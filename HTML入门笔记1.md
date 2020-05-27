# HTML的由来

HTML的英文全称是 Hyper Text Marked Language，即超文本标记语言。  
HTML是由Web的发明者 Tim Berners-Lee（李博士）于1990年创立的一种标记语言。

# HTML起手怎么写

    !

注意是英文的感叹号再Tab键展开就好了如下：
~~~HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
~~~

# 章节标签有哪些

标题 h1-h6  
章节 section  
文章 article  
段落 p  
头部 header  
脚部 footer  
主要内容 main  
旁支内容 aside  
划分 div  

# 全局属性有哪些

class  
contenteditable（用户可以编辑网页）  
hidden  
id  
style  
tabindex（Tab键选取：-1表示不可选取；0表示最后被选取；正数按大小顺序选取）  
title（鼠标移上去显示完整内容）  

# 常用的内容标签

## ol + li —— 有序列表和列表项  
~~~HTML
<ol>
    <li>唱歌</li>
    <li>跳舞</li>
    <li>Rap</li>
    <li>篮球</li>
</ol>
~~~
![有序列表页面展示](https://github.com/Amber-Tian/blog-test/blob/master/images/ol.png)

## ul + li —— 无序列表和列表项  
~~~HTML
<ul>
    <li>唱歌</li>
    <li>跳舞</li>
    <li>Rap</li>
    <li>篮球</li>
</ul>
~~~
![无序列表页面展示](https://github.com/Amber-Tian/blog-test/blob/master/images/ul.png)

## dl + dt + dd —— 描述列表
~~~HTML
动物园里面有什么
<dl>
    <dt>老虎<dt>
    <dd>大型猫科动物<dd>
<dl>
~~~

## pre —— 保留标签里面的所有字符
## hr —— 分割线
## br（break） —— 换行
## a —— 链接
## em —— 语气强调（字体变斜）
## strong —— 强调本身（字体变粗）
## code —— 标签里面写代码，特点是每个字符宽度相同，常和pre标签联用
## q（quote） —— 引用，内联元素
## blockquote —— 块级引用
