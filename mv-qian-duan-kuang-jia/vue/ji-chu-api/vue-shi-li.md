---
description: 创建和作用
---

# VUE实例

## 实例的创建和作用

挂载vue实例的方法1

```text
import Vue from 'vue'

new Vue({
  el:'#root',
  template: '<div>this is content</div>'
})

```

挂载vue实例方法2:

```text
const app=new Vue({
  //el:'#root',
  template: '<div>this is content</div>'
})
app.$mount('root')
```

```javascript
//我们看一使用的例子;
const app=new Vue({
  template: '<div>this is content</div>',
  data:{
    text:0
  }
})
app.$mount('#root')

setInterval(()=>{
  app.text+=1
},1000)
```

## 实例的属性

```javascript
// 属性:
console.log(app.$data)//实例的原数据
console.log(app.$props)// 在组件传值的时候会使用到
console.log(app.$el)//对用的html的节点
console.log(app.$options)//可以传入的参数
// 只有再次渲染的时候才能 render
app.$options.render = (h)=> {
  return h("div", {}, "new render function")
}
console.log(app.$root)
console.log(app.$root === app)//true

console.log(app.$children)//<item><div></div></item> 就是里面的div

console.log(app.$scopedSlots) //插槽
console.log(app.$slots)

console.log(app.$refs)//用于快速找到实例

console.log(app.$isServer)//服务端渲染时候用到
```

## 实例的方法

```text
// 方法:
// 当然也可以写在实例里面,
const unWatch = app.$watch('text', (newText, oldText)=> {
  console.log(`${newText}:${oldText}`)
});
//注销 watch
setTimeout(()=> {
  unWatch()
}, 5000);

// 事件监听 once 只触发一次
app.$on('test',(a,b)=>{
  console.log('test emited',a,b)
});
app.$emit('test',1,2);
//强制组件进行跟新
app.$forceUpdate()
//连续修改了dom 事件之后.做dom跟新
app.$nextTick()
app.$set(app.obj, "a", i) //给新的值赋值
```

