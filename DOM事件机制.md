# DOM事件机制

## 一、DOM事件模型和事件流

### 定义

事件流描述的是从页面中接受事件的顺序，也可以理解为事件在页面中传播的顺序

<img src="https://github.com/Amber-Tian/blog-test/tree/master/images/event.png" alt="事件流示意图" height="200px">

这两个事件流分别的是IE公司和网景公司提出来的，冒泡事件流支持的浏览器更多。 

事件捕获阶段：事件从最上一级标签开始往下查找，直到捕获到事件目标(target)。
事件冒泡阶段：事件从事件目标(target)开始，往上冒泡直到页面的最上一级标签。

### DOM事件捕获的流程示意图（冒泡相反）

<img src="https://github.com/Amber-Tian/blog-test/tree/master/images/catch.png" alt="事件捕获示意图" height="200px">

### 语法

~~~js
DOM元素.addEventListener('事件', fn(), false) // 默认冒泡，第三个参数是false可不写

DOM元素.addEventListener('事件', fn(), true) // 捕获
~~~

### event对象的常见应用

1. e.preventDefault()

   阻止默认事件，比如a标签跳转、submit按钮提交等

~~~js
dom.addEventListener('click', (e)=>{
    e.preventDefault()
}, false)
~~~

2. e.stopPropagation() 

   阻止冒泡，有特例scroll无法阻止， 可使用css隐藏滚动条，但此时js仍可操作性scrollTop，再用wheel和touchStart阻止默认事件就可以了

3. e.target
   
   target 事件属性可返回事件的目标节点（触发该事件的节点），如生成事件的元素、文档或窗口。

4. e.currentTarget
   
   currentTarget 事件属性返回其监听器触发事件的节点，即当前处理该事件的元素、文档或窗口。  

   在捕获和起泡阶段，该属性是非常有用的，因为在这两个节点，它不同于 target 属性。

   与event.target的区别
   
   event.currentTarget指向事件所绑定的元素，而event.target始终指向事件发生时的元素

## 二、事件委托（事件代理）

由于事件会在冒泡阶段向上传播到父节点，因此可以把子节点的监听函数定义在父节点上，由父节点的监听函数统一处理多个子元素的事件。这种方法叫做事件的委托。

### 优点

1. 减少内耗，提升性能

假设有一个列表，列表之中有大量的列表项，我们需要在点击每个列表项的时候响应一个事件

~~~js
<ul id="list">
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
  ......
  <li>item n</li>
</ul>
~~~

如果给每个列表项一一都绑定一个函数，那对于内存消耗是非常大的，效率上需要消耗很多性能。借助事件委托，我们只需要给父容器ul绑定方法即可，这样不管点击的是哪一个后代元素，都会根据冒泡传播的传递机制，把容器的click行为触发，然后把对应的方法执行，根据事件源，我们可以知道点击的是谁，从而完成不同的事。

2. 动态绑定事件

在很多时候，我们需要通过用户操作动态的增删列表项元素，如果一开始给每个子元素绑定事件，那么在列表发生变化时，就需要重新给新增的元素绑定事件，给即将删去的元素解绑事件，如果用事件委托就会省去很多这样麻烦。

### 实例实现

~~~js
// 给父层元素绑定事件
document.querySelector('#list').addEventListener('click', function (e) {
  // 判断是否匹配目标元素
  if (e.target.nodeName.toLocaleLowerCase === 'li') {
    console.log(`the content is: ${e.target.innerHTML}`);
  }
});
~~~

## 三、自定义事件

1. Event()
~~~js
// 创建一个支持冒泡且不能被取消的look事件

const ev = new Event("look", {"bubbles":true, "cancelable":false});

//分发事件给document
document.dispatchEvent(ev);

// 事件可以在任何元素触发，不仅仅是document
myDiv.addEventListener('look', ()=>console.log('hi'))
myDiv.dispatchEvent(ev);
~~~
 
 2. customEvent() 有detail属性可以传递数据
~~~js
// 创建一个支持冒泡且不能被取消的look事件
const event = new CustomEvent('look', {
  detail: {name: 'look', attribute: 'newEvent', others: 'Hello'},
  bubbles: true,
  cancelable: false
})

//添加一个适当的事件监听器
dom.addEventListener('look', (e)=>{
    console.log('look事件触发了')
    console.log(e.detail)
})

//分发事件给dom
dom.dispatchEvent(event)
~~~
 
