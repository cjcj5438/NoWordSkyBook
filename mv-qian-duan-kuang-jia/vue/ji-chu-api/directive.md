---
description: vue 原生指令
---

# directive

```javascript
import Vue from 'vue'

new Vue({
  el: '#root',
  template: `
    <div>
      <div>Text: {{text}}</div>
      <div v-if="text === 0">Else Text: {{text}}</div>
      <div v-else>else content</div>
      <div v-html="html"></div>
      <input text="text" v-model="text">
      <input type="checkbox" v-model="active">
      <div>
        <input type="checkbox" :value="1" v-model="arr">
        <input type="checkbox" :value="2" v-model="arr">
        <input type="checkbox" :value="3" v-model="arr">
      </div>
      <div>
        <input type="radio" value="one" v-model="picked">
        <input type="radio" value="two" v-model="picked">
      </div>
      /*
        :key="item"  比如我们渲染一个列表时候为了减少每次重新排版列表造成性能开销,
        所以我们要加一个:key 来做缓存.当有了新数据的时候可以直接找到位置然后替换, 对应的值我
        们一般采用 item 不使用index
        */
      <ul>
        <li v-for="(item, index) in arr" :key="item">{{item}}:{{index}}</li>
      </ul>
      <ul>
        <li v-for="(val, key, index) in obj">{{val}}:{{key}}:{{index}}</li>
      </ul>
    </div>
  `,
  data: {
    arr: [2, 3],
    obj: {
      a: '123',
      b: '456',
      c: '789'
    },
    picked: '',
    text: 0,
    active: false,
    html: '<span>this is html</span>'
  }
})


// v-model.lazy 相当于change事件
// v-pre 写什么显示什么
// v-cloak
// v-once 数据绑定只执行一次.节省一点性能开销

```

