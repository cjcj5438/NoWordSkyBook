---
description: >-
  /*组件的继承的两种方法.一般我们写了 公用组件之后.不需要这么多配置项或者是扩展* 一些配置项的时候, 我们就可以用组件继承
  而不需要重新写一个组件*//*补充一点$parent 的知识*/
---

# 组件继承

```c
import Vue from 'vue'
const parent = new Vue({
  name: 'parent'
})
const compoent = {
  props: {
    active: Boolean,
    propOne: {
      required:false
    }
  },
  template: `
    <div>
      <input type="text" v-model="text">
      <span @click="handleChange">{{propOne}}</span>
      <span v-show="active">see me if active</span>
    </div>
  `,
  data () {
    return {
      text: 0
    }
  },
  methods: {
    handleChange () {
      this.$emit('change')
    }
  },
  mounted(){
    console.log('comp1 mounted')
    console.log(this.$parent.$options.name)
    // 通过parent可以修改父组件的内容, 查看一些东西但是不建议改 ,
    this.$parent.text='12345'
  }
}

```

```javascript
//继承二
const componet2={
  extends:compoent,
  data(){
    return {
      text:1
    }
  },
  mounted(){
    console.log('comp2 mounted')
  }
}

new Vue({
  parent: parent,
  name: 'Root',
  el:'#root',
  components:{
    Comp:componet2
  },
  data: {
    text: 23333
  },
  template: `
    <div>
      <span>{{text}}</span>
      <comp></comp>
    </div>
  `
})
```



```csharp
//继承1
const CompVue=Vue.extend(compoent)

new CompVue({
  el:"#root" ,
  /*不要直接写props 虽然不会报错,但是不会显示*!/
  propsData:{
    propOne:'xxx'
  },
  //data 就可以直接修改默认值
  data:{
    text:1234
  },
  mounted(){
    console.log('instance mounted')
  }
})

```

