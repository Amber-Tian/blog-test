# JS对象基本用法

## 声明对象
1. 对象字面量
~~~JS
let obj = {'name': 'Tom', 'age': '18'}
~~~
2. new Object
~~~JS
let obj = new Object({'name': 'Tom', 'age': '18'})
~~~

## 如何删除对象的属性
* delete obj.属性名 或 delete obj['属性名']
* 注意点：obj.xxx === undefined 不能断定obj是否含有xxx属性

## 如何查看对象的属性
1. 查看自身属性：
   * Object.keys(obj) 查看obj的所有属性名
   * Object.values(obj) 查看obj的所有属性值
   * Object.entries(obj)
     ~~~JS
        var obj = {'name': 'Tom', 'age': '18', 'gender': '男'};
        console.log(Object.entries(obj))

        /*打印结果：
         (3) [Array(2), Array(2), Array(2)]
           0: (2) ["name", "Tom"]
           1: (2) ["age", "18"]
           2: (2) ["gender", "男"]
        */
     ~~~
2. 查看共有属性
   * console.dir(obj)

## 如何修改或增加对象的属性
1. 直接赋值
~~~JS
  let obj = {'name': 'Tom', 'age': '18'};
  obj.gender = '男';
  obj.name = 'Jerry';
  obj['name'] = 'Jerry';
  obj['na'+'me'] = 'Jerry';
  let key = 'name'; obj[key] = 'Jerry'
~~~
2. 批量赋值
   * Object.assign(obj, {'age': '18', 'gender': 'mam'})

3. 修改共有属性
   * obj.__proto__.toString = 'xxx'  //不推荐使用__proto__
   * Object.prototype.toString = 'xxx'
   * 一般来说不要修改原型，会引起很多问题

4. 增加隐藏属性
~~~JS
 let common = {'kind': 'human'}
 let obj = Object.create(common)
 obj.name = 'Tom'
~~~

## 'name' in obj 和 obj.hasOwnProperty('name')的区别
* 两者都可以用来判断name是不是obj的属性，但是后者只能判断是不是本身的属性，如果是原型属性后者不能判断