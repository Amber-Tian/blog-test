# JS的基本语法学习总结

## 表达式与语句
* 1 + 2 表达式的值为3
* add(1,2)表达式的值为函数的返回值
* console.log表达式的值为函数本身
* console.log(3)会打印一个3但是表达式本身返回值是undefined
* var a=1是一个语句

### 二者区别
* 表达式一般都有值，语句可能有也可能没有
* 语句一般会改变环境（声明、赋值）

## JS注意点

### 大小写敏感
* var a和var A是不同的
* object和Object是不同的

### 空格和回车
* 大部分空格和回车没有实际意义也没有影响
* 只有一个地方不能加回车，那就是return后面，加完函数返回值为undefined

## 变量命名规则
第一个字符可以是Unicode字母或$或_或中文，后面的字符除了前面说的还可以是数字

## 注释
1. // 这是注释内容
2. /* 这是注释内容 */
3. 写一些有意义的注释比如自己出过的错、看起来很起怪的代码或者遇到的bug

## if语句
* 大括号可以省略但是最好不要省，程序员戒律使用最没有歧义的写法
* 语法
~~~JavaScript
  if(表达式) {
      语句1;
  } else if(表达式) {
      语句2;
  } else {
      语句3;
  }
~~~

## switch语句
* 注意不要省略break
* 语法
~~~JS
  switch (expression) {
    case value1:
      // 当 expression 的结果与 value1 匹配时，执行此处语句
      break;
    case value2:
      // 当 expression 的结果与 value2 匹配时，执行此处语句
      break;
    ...
    case valueN:
      // 当 expression 的结果与 valueN 匹配时，执行此处语句
      break;
    default:
      // 如果 expression 与上面的 value 值都不匹配，执行此处语句
      break;
  }
~~~

## for语句
* 注意循环条件不要出错以防进入死循环
* 语法
~~~js
for (var i = 0; i < 9; i++) {
   console.log(i);
   // more statements
}
~~~
* for 语句头部圆括号中的所有三个表达式都是可选的，但是必须确保在循环体内跳出，以防创建死循环

## break和continue
* break 语句中止当前循环，并把程序控制流转到紧接着被中止语句后面的语句
* continue 终止当前循环或标记循环的当前迭代中的语句执行，并在下一次迭代时继续执行循环
* 注意点：如果是嵌套循环break只是终止最近的循环不影响外面的循环

## label
语法
~~~js
label : {
   statement
}
foo: {
    console.log(1);
    break foo;
    console.log("本行不会输出");
}
console.log(2);
/*打印结果：
1
2
*/
~~~