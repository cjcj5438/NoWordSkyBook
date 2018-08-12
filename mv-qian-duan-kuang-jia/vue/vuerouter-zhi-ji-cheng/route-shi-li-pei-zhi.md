# route 实例配置



```text
import Router from 'vue-router'
import routes from './routes'

// const router = new Router({
//   routes
// })
//
// export default router
/* 在服务端渲染的时候,会导致溢出,所有这样导出 */
export default () => {
  return new Router({
    routes,
    /*默认是hash路由. 配置history*/
    mode: 'history',
    // 配置router基础路径
    base: '/base/',
    /*区别 :/login/exact
    * 匹配一部分路由:/login  linkActiveClass
    * 路由完全匹配:/login/exact linkActiveClass
    * */
    linkActiveClass: 'active-link',
    linkExactActiveClass: 'exact-active-link',
    // 就是页面跳转的时候要不要接受滚动的问题
    /**
     * scrollBehavior
     * @param to 要去哪个路由
     * @param from 从哪个路由跳转
     * @param savedPosition 就是滚动条会记录这个位置
     */
    scrollBehavior(to, from, savedPosition) {
      if (savedPosition) {
        return savedPosition
      } else {
        return {x: 0, y: 0}
      }
    },
    /*Query 是url后面跟的参数*/
    /* parseQuery 是把字符串转成json object 的方法*/
    parseQuery(query){},
    stringifyQuery(obj){},
    fallback:true
  })

}
```

