---
description: console.log(this.$route)
---

# 参数传递





```text
import Todo from '../views/todo/todo.vue'
import Login from '../views/login/login.vue'
export default [
  // 默认是hash路由:一般是用来做定位的,而不是做路由状态的一个记录,而且不会被搜索引擎解析的,会导致网站的seo非常不好
  {
    /*默认路由*/
    path: '/',
    component: Todo
  },
  {
    path: '/app/:id',
    component: Todo,
    /*路由命名
    * name:xxx
    * 怎么使用呢 <router-link :to="{name:app}">app</router-link>
    */
    name:'app',
    /*mete 用来保存路由里面的信息的
    * 页面的源信息 就是页面head标签里面的信息
    * 因为在组件里面很难写.*/
    mete:{
      title:'this is app',
      description:"xxxxxx"
    },
    /*嵌套路由*/
    children:[
      {
        path: 'test',
        component: Login
      },
    ],
    /*transition 动画*/
    /*路由传参
    * 那有会有什么用呢? 比如说我们在商品列表选中一个商品,要跳转详情页 ,这个时候就可以把参数带过去
    * 还有就是query url问号后面的参数
    * 还有更简单方法 props
    * */
    /*props三种方式实现*/
    // props:true,//可以把路由的 参数传到组件里面去
    /*props:{
      id:'xxx'
    }*/
   /* props:(route)=>{
      {id:route.query.b}
    }*/

  },
  {
    path: '/login',
    component: Login
  }
]

```

```text
/*props三种方式实现*/
 1, props:true,//可以把路由的 参数传到组件里面去
 2, props:{
      id:'xxx'
    
 3,  props:(route)=>{
      {id:route.query.b}
    }
```

```text
transition 动画

//*.vue
<transition name="fade">
      <router-view></router-view>
</transition>

//*.styl
.fade-enter-active, .fade-leave-active
  transition opacity .5s

.fade-enter, .fade-leave-to
  opacity: 0
```

