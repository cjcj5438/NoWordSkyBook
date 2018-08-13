# 模块

## **多模块间的操作**

```text
modules: {
      a: {
        /*开启命名空间*/
        namespaced: true,
        state: {
          text: 1
        },
        mutations: {
          updateText(state, text) {
            console.log('a.text', state)
            state.text = text
          }
        },
        getters: {
          /**
           *
           * @param state 当前state
           * @param getters 当前所有的getter方法
           * @param rootState 全局state
           * @returns {*}
           */
          textPlus(state, getters, rootState) {
            return state.text + rootState.count + rootState.b.text
          }
        },
        actions: {
          // add(ctx){
          //   /*可以拿到执行上下文*/
          //   console.log(ctx)
          // }
          add({state, commit, rootState}) {
            /*操作根state */
            commit('updateText', rootState.count)
            /*如果要用根的mutations里面方法要加{root:true}:*/
            commit('updateCount', {num1: 987654}, {root: true})

          }
        }
      },
      b: {
        state: {
          text: 1
        },
        actions: {
          testAction({commit}) {
            commit('a/updateText', 'b操作a的mutations', {root: true})
          }
        }
      }
    }
```

use

```text
export default {
    computed: {
      // testA(){
      //   return this.$store.state.a.text;
      // },
 
      ...mapState({
        count: 'count',
        testA: state => state.a.text,
        testB: state => state.b.text,
        testC: state => state.c.text
      }),
    
      ...mapGetters({
        fullName: "fullName",
        textPlus: 'a/textPlus'
      })
    },
    mounted() {   
      // this.updateText('123')
      this['a/updateText']('123')
      this['a/add']()
      this.testAction()
    },

    methods: {
      ...mapMutations(['updateCount', 'a/updateText']),
      ...mapActions(['updateCountAsync', 'a/add', 'testAction'])
    }
```

## 动态注册store

```text
//main.js
store.registerModule('c',{
  state:{
    text:"c"
  }
})
```

```text
store.unregisterModule('c') //取消注册
```

## 热更替 .

> 在修改state的时候不用刷新页面

```text
//store.js
// store热更替
  if (module.hot) {
    module.hot.accept([
      './state/state',
      './mutations/mutations',
      './getters/getters',
      './actions/actions'
    ], () => {
      // 这里不能写import ,因为import只能在代码的最外层,不能在代码逻辑层写
      const newState = require('./state/state').default
      const newMutations = require('./mutations/mutations').default
      const newGetters = require('./getters/getters').default
      const newActions = require('./actions/actions').default

      store.hotUpdate({
        state: newState,
        getters: newGetters,
        mutations: newMutations,
        actions: newActions
      })
    })
```

