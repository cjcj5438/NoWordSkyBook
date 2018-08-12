# vuex集成



```javascript
//store.js
import Vuex from 'vuex'

// const store=new Vuex.Store({
//   state:{
//     count:0,
//   },
//   mutations:{
//     updateCount(state,num){
//       state.count=num
//     }
//   }
// })
//
// export default store
export default ()=>{
  return new Vuex.Store({
    state:{
      count:0,
    },
    mutations:{
      updateCount(state,num){
        state.count=num
      }
    }
  })
}

```

```javascript
//main.js
import Vue from 'vue'
import Vuex from 'vuex'
import App from './app.vue'


import './assets/styles/global.styl'
import createRouter from './config/router'
import createStore from './store/store'

Vue.use(Vuex)

// const root = document.createElement('div')
// document.body.appendChild(root)

const store = createStore()
new Vue({
  router,
  store,
  render: (h) => h(App)
}).$mount('#root')

```

```javascript
//use
 export default {
    mounted(){
      console.log(this.$store)
      let i=1;
      setInterval(()=>{
        this.$store.commit('updateCount',i++)
      },1000)
    },
    computed:{
      count(){
        return this.$store.state.count
      }
    }
  }
```

