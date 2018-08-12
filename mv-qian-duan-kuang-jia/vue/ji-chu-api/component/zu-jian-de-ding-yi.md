# 组件的定义

> props 值的处理 单向数据流概念

{% tabs %}
{% tab title="父组件改子组件的值" %}
```javascript
//父:
<comp-one :active="true" propOne="text2"></comp-one>
```

```text
 props: {
    active: {//...
    }
 }
 来约束父组建传的值
```
{% endtab %}

{% tab title="子组件改父组件的值,需要通过事件触发的方式" %}
```text
 //子组建
 template: `
    <div>
      <span @click="handleChange">{{propOne}}</span>
    </div>
  `,
  methods: {
    handleChange () {
      this.$emit('change')
    }
```

```text
//父组件
new Vue({
  components: {
    CompOne: compoent
  },
  data: {
    prop1: 'text1'
  },
  methods: {
    handleChange () {
      this.prop1 += 1
    }
  },
  mounted () {
    console.log(this.$refs.comp1)
  },
  el: '#root',
  template: `
    <div>
      <comp-one ref="comp1" :prop-one="prop1" @change="handleChange"></comp-one>
    </div>
  `
})
```
{% endtab %}
{% endtabs %}

```javascript
import Vue from 'vue'

const compoent = {
/*props有什么用?
  * 是用来定义这个组件,在被外部使用的时候,他的一些可变的行为,也就是说,我去定义一个组件的时候
  * 希望这个组件帮我们解决一些通用型的问题,就是说这个组件包含某个功能,主要的目的,就是
  * 处理这些功能,需要不同的配置项,来配置组件的行为,通过props实现可配置的行为
  * 还有就是不能被改,  外部组件约束内部组件的行为的, 相当于就是父组件向子组件传值
  * */
  props: {
    active: {
      // type: Boolean,
      // required: true,
      //如果使用的是一个对象,那么default 返回一个方法
      // default:{}
      /*default(){
        return {}
      },*/
      //还可以更严格的判断.
      validator (value) {
        return typeof value === 'boolean'
      }
    },
    propOne: String
  },
  template: `
    <div>
      <input type="text" v-model="text">
      <span @click="handleChange">{{propOne}}</span>
      <span v-show="active">see me if active</span>
    </div>
  `,
  /*如果我们这个组件不是通过new Vue() 这种方式生成的
  * 而是通过全局注册或者局部注册的时候去使用的话,要写成function(){}
  * 的方法
   data:{  不对的写法
    text:123
  }*/
  data () {
    return {
      text: 0
    }
  },
  methods: {
    handleChange () {
      this.$emit('change')
    }
  }
}
/*vue 官方建议这样注册组件名组件就是一个类
 全局注册组件*/
// Vue.component('CompOne', compoent)

new Vue({
  components: {
    CompOne: compoent
  },
  data: {
    prop1: 'text1'
  },
  methods: {
    handleChange () {
      this.prop1 += 1
    }
  },
  mounted () {
    console.log(this.$refs.comp1)
  },
  el: '#root',
  template: `
    <div>
      <comp-one ref="comp1" :active="true" :prop-one="prop1" @change="handleChange"></comp-one>
      <comp-one :active="true" propOne="text2"></comp-one>
    </div>
  `
})

```

