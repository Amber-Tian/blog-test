~~~js
new Vue({
    el: "#app",
    data: {
        obj: {
            a: 0 // obj.a 会被 Vue 监听 & 代理
        }
    },
    template: `
        <div>
            <span>{{obj.a}}</span>
            <button @click="add">+1</button>
            <br/>
            <span>{{obj.b}}</span>
            <button @click="setB">set b</button>
        </div>
    `,
    methods: {
        add() {
            this.obj.a += 1
        },
        setB() {
            this.obj.b = 100
        }
    }
})
~~~

当new Vue在实例化的时候，首先将data方法里返回的对象属性都用[Object.defineProperty](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)挂载上setter方法，而setter方法里将页面上的属性进行绑定，当页面加载时，浏览器调用mounted挂载函数，开始获取接口数据，获取完成后给data里属性赋值，赋值的时候触发前面挂载好的setter方法，从而引起页面的联动，达到响应式效果。

但是需要注意的是Vue只会检查第一层属性，如上例点击set b按钮页面并不会渲染出100，因为Vue没法监听一开始不存在的obj.b

Vue提供了set方法解决这类问题
~~~js
//setB改写
setB() {
    Vue.set(this.obj, 'b', 100) // 或 this.$set(this.obj, 'b', 100)
}
~~~

上面方法解决了对象内未提前声明的属性的响应问题，但是该方法对长度变化的数组来说就比较臃肿了

此时可以直接使用[变更方法](https://cn.vuejs.org/v2/guide/list.html#%E5%8F%98%E6%9B%B4%E6%96%B9%E6%B3%95)中的push

~~~js
new Vue({
    el: "#app",
    data: {
        array: ["a", "b", "c"]
    },
    template: `
        <div>
            {{array}}
            <button @click="setD">set d</button>
        </div>
    `,
    methods: {
        setD() {
            this.array.push("d");
        }
    }
})
~~~