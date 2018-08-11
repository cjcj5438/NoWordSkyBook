---
description: '介绍基本的生命周期, 在后面会详细介绍'
---

# 生命周期

```javascript
import Vue from 'vue'

const app=new Vue({
  template: '<div>this is content-{{text}}</div>',
  data:{
    text:0
  },
  beforeCreate(){
    console.log(this,'beforeCreate')
  },
  created(){
    console.log(this,'created')
  },
  beforeMount(){
    console.log(this,'beforeMount')
  },
  mounted(){
    console.log(this,'mounted')
  },
  beforeUpdate(){
    console.log(this,' beforeUpdate')
  },
  beforeUpdate(){
    console.log(this,'beforeUpdate')
  },
  updated(){
    console.log(this,'updated')
  },
  activated(){
    console.log(this,'activated')
  },
  deactivated(){
    console.log(this,'deactivated')
  },
  beforeDestroy(){
    console.log(this,'beforeDestroy')
  },
  destroyed(){
    console.log(this,'destroyed')
  }
})

app.$mount('#root')

// setInterval(()=>{
//   app.text++;
// },1000)

setInterval(()=>{
  //主动销毁. 为取消监听,
  app.$destroy()
},1000)


// activated,deactivated 组件的keep-alife 我在后面的组件会详细介绍



```

