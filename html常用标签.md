# a标签

## href

href 的取值有以下几种：
1. 网址：
   * https://xxx.com
   * http://xxx.com
   * //xxx.com
    推荐使用第三种它会自动找到合适的协议

2. 路径：
   * 相对路径绝对路径都可以（/a/b/c和a/b/c）
   * index.html以及./index.html

3. 伪协议：
   * javascript：代码; (点击a标签会运行代码内容，如果代码处为空则不进行任何跳转)
   * mailto:邮箱 (点击a标签跳转发邮件)
   * tel:手机号
 
4. id:
   * href=#xxx  (点击会跳转到id处) 

## target（个人理解就是命名窗口）

1. 内置名字
   * _blank 新窗口打开
   * _self 当前窗口打开（默认值）
   * _top 当前页面的子孙窗口内点击会在当前页面打开
   * _parent 子窗口点击在父窗口打开

2. 扩展命名
   ~~~html
   <a href="//google.com" target="xxx">google</a>

   <a href="//baidu.com" target="xxx">baidu</a>
   ~~~
   第一次点击会在新窗口打开名叫“xxx”的窗口，后面点击就会覆盖前面的页面，因为它也要在xxx页面打开。  

   ~~~html
   <a href="//baidu.com" target="xxx">baidu</a>

   <iframe href="" target="xxx">baidu</iframe>
   ~~~
   这样点击baidu会在本页面的子窗口打开百度主页，因为它们target关联。

## download
点击不会打开新的页面而是进入下载页面，不是所有浏览器都支持，尤其是手机浏览器。

# table标签

## 相关标签

* thead
* tbody
* tfoot
* tr(tale-row, 表格行)
* td(table-data, 单元格)
* th

## 相关样式

* border-collapse: collapse;
* border-spacing: 0;
两个基本会在样式reset里面加入，都是设置单元格间隙的，一般不需要单元格之间留空隙会很难看。

# img标签

## 作用
发送一次get请求，展示一张图片。

## 属性
* alt：描述图片（图片加载失败会显示描述文字）
* height：设置图片高度
* width：设置图片宽度
* src：图片的路径

## 事件
图片加载成功onload，失败onerror（请求另一个地址补救）

## 响应式
设置max-width: 100%;

# form标签

## 作用
发送get或post请求，然后刷新页面

## 属性
* action
* autocomplete=on/off; 表示是否自动填写
* method=get/post; 选择请求方式
* target 表单提交到哪里

## 事件
* onsubmit
~~~html
<input type="submit" value="提交">

<button type="submit" value="提交">提交</button>
~~~
两个点击都可以触发onsubmit事件，区别在于button标签内可以包含别的标签例如：img、strong等

# input标签

## 作用
让用户输入内容

## 属性
* 类型type: button/checkbox/email/file/hidden/number/password/text/radio/search/submit/tel/
* 其他name/autofocus/checked/disable/maxlength/pattern/value/placeholder

## 事件
onchange/onfocus/onblur