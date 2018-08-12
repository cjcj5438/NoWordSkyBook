# 双向数据绑定

> 在一个组建里面加了props 里面有一个value 然后在特定的一个时机我们加了input 监听事件,组件要去修改这个数据的时候通过$emit 把一个新的值 传给父组件 这样就实现了一个双向数据绑定其实 v-model 指令, 就是帮我们加了一个 value 的props 和一个事件监听input ,然后v-model帮我处理双向绑定的逻辑

```text
import Vue from "vue";

const component = {
/*v-model 功能不止这些. 有时候我们又要加value 又要做双向数据绑定,就会和props 冲突
* 答案是有解决方案的. 在组建定义的时候加model 属性
* */
  model:{
    prop:'value1',
    event:'change'
  },
  // props: ['value'],
  props: ['value1'],
  template: `
    <div>
    <input type="text" @click="handleInput" :value="value1"> 
</div>
  `,
  methods: {
    handleInput(e) {
      // this.$emit('input', e.target.value)
      this.$emit('change', e.target.value)
    }
  }
}

new Vue({
  components: {
    CompOne: component
  },
  el: '#root',
  data() {
    return {
      value: '1234'
    }
  },
  template: `
    <div>
    <!--<comp-one :value="value" @input="value=arguments[0]"></comp-one>-->
    <comp-one v-model="value"></comp-one>
</div>
  `
})
```

