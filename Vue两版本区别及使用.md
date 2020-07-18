在使用Vue的时候，分为两个版本，一个是完整版（vue.js）,另一个是非完整版也叫运行时版本（vue.runtime.js）

### 主要区别

完整版有compiler，编译器主要是将模板字符串编译成JS渲染字符串，导致完整版体积过大。

非完整版没有compiler，体积小，大约小30%-40%左右。

### 引入区别

在(bootcdn)[bootcdn.cn]搜索。

完整版引入： vue.js，生产环境下引入vue.min.js

非完整版引入：vue.runtime.js，生产环境下引入vue.runtime.min.js

### 视图

完整版：
视图写在html里或者template选项里，由于有compiler（编译器）的存在，完整版运行时，用来创建Vue实例，渲染并处理虚拟DOM等代码。
~~~js
Vue({
  el: '#app',
  template: `<div>{{n}}</div>`,
  data(){
    return {
          n: 0
      }
   }
})
~~~

非完整版：
当使用 vue-loader 或 vueify 的时候，*.vue 文件内部的模板会在构建时预编译成 JavaScript。你在最终打好的包里实际上是不需要编译器的，所以只用运行时版本即可。
~~~js
Vue( {
  el: '#app',
  render(h){
    return h('div',this.n)
  },
  data(){
    return {
      n: 0
    }
  }
})
~~~

### 其他

* webpack引入：Vue完整版需要配置alias,Vue非完整版默认使用
* @vue/cli引入，完整版需要额外配置，默认使用非完整版。

### 总结

总是使用非完整版，然后配合使用vue-loader和vue文件。
理由：
* 保证用户体验，用户下载的js体积更小，但只支持h函数
* 保证开发体验，开发者可直接在vue文件里写HTML标签，而不写h函数
* 事情让loader做，vue-loader把vue文件里的HTML转换为h函数