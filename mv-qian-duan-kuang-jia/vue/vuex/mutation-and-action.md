# mutation & action

## 集成

```text
 *.vue
     mounted() {
      let i = 1;

            setInterval(() => {
              /!*commit 后面只能传一个参数,如果要传多个参数可以用对象包裹*!/
              // this.$store.commit('updateCount', i++)
              this.$store.commit('updateCount', {
                num1:i++,
                num2:0
              })
            }, 1000)

      this.$store.dispatch('updateCountAsync', {
        num1: 3,
        time: 0
      }) 
```

```text
//actions.js
export default {
  updateCountAsync(store, data) {
    setTimeout(() => {
      store.commit('updateCount', {num1: data.num1})
    }, data.time)
  }
}

```

```text
//mutations.js
export default {
  /*vue 官方推荐所有的state操作都要放在mutations里面  但是在外面也可以修改*/
  updateCount(state, {num1, num2}) {
    console.log(num1, num2)
    state.count = num1
  }
}

```

```text
main.js
import Vuex from 'vuex'

import defaultState from './state/state'
import mutations from './mutaitions/mutations'
import getters from './getters/getters'
import actions from './actions/actions'

const isDev = process.env.NODE_ENV === 'development'
export default () => {
  return new Vuex.Store({
    /* 添加这个配置 就无法重外部修改数据
    这是代码规范
    开发时候可以使用, 正式上线的时候不建议 */
    strict: isDev,

    state: defaultState,
    mutations,
    getters,
    actions
  })
}

```

## mapActions, mapMutations 辅助方法

```text
import {mapState, mapGetters, mapActions, mapMutations} from 'vuex'

    mounted() {
      /*...map 帮助方法之后*/
      setInterval(() => {
        this.updateCount({
          num1: i++,
          num2: 2
        })
      }, 1000)

      this.updateCountAsync({
        num1: 3,
        time: 0
      })

    },
  methods: {
      ...mapMutations(['updateCount']),
      ...mapActions(['updateCountAsync'])
    }
```

