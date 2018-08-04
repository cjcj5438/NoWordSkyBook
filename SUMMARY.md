# Summary

* [Introduction](README.md)
* [First Chapter](chapter1.md)

## 算法&数据结构

* 基础
  * [队列](arithmetic/duilie.md)
  * [集合](arithmetic/jihe.md)
  * [列表](arithmetic/liebiao.md)
  * [栈](arithmetic/zhan.md)
  * [字典](arithmetic/zidian.md)
  * 散列
    * [散列介绍](arithmetic/sanlei/sanlie.md)
    * [开链法](arithmetic/sanlei/sanliekailianfa.md)
    * [线性探测法](arithmetic/sanlei/sanlietancefa.md)
  * 链表
    * [链表介绍](arithmetic/lianbiao/lianbiao.md)
    * [单向链表代码实现](arithmetic/lianbiao/lianbiaodanxiang.md)
    * [双向链表代码实现](arithmetic/lianbiao/lianbiaoshuangxiang.md)

## CSS

* sass
  * 使用手册
    * [速查手册](CSS/sass/kuaisushiyong.md)

## 编程语言

* NodeJS
  * 基础API
    * [回调函数](NodeJS/base/bc.md)
    * [事件驱动机制](NodeJS/base/loop.md)
    * [模块化](NodeJS/base/module.md)
    * [函数](NodeJS/base/func.md)
    * [路由](NodeJS/base/route.md)
    * [全局方法和工具](NodeJS/base/global.md)
    * [文件系统](NodeJS/base/file.md)
  * Express
  * KOA2
  * EGG
  * NodeJS线上部署
  * 阅读NodeJS源代码
  * 大规模NodeJS架构与优化
    * [异步IO原理浅析以及优化方案](NodeJS/plus/asyncIO.md)
    * [内存管理机制及内存优化](NodeJS/plus/neicun.md)
    * [大规模node站点结构原理分析](NodeJS/plus/nodeHost.md)
    * [服务器集群管理与node集群的应用](NodeJS/plus/jiqun.md)
    * [UV过千万的node站点真身](NodeJS/plus/uv1000.md)
* python
  * [python3快速入门](python3/base/base.md)
* ES6
  * reflect 反射
    * [概述](js/ES6/reflect/gaisu.md)
    * [静态方法](js/ES6/reflect/jingtaifangfa.md)
    * [实例](js/ES6/reflect/shili.md)
  * Promise 对象
    * [Promise 的含义](js/ES6/Promise/hanyi.md)
    * [基本用法](js/ES6/Promise/base.md)
    * [&.prototype.then\(\)](js/ES6/Promise/then.md)
    * [&.prototype.catch\(\)](js/ES6/Promise/catch.md)
    * [&.prototype.finally\(\)](js/ES6/Promise/finally.md)
    * [&.all\(\)](js/ES6/Promise/all.md)
    * [&.race\(\)](js/ES6/Promise/rece.md)
    * [&.resolve\(\)](js/ES6/Promise/resolve.md)
    * [&.reject\(\)](js/ES6/Promise/reject.md)
    * [应用](js/ES6/Promise/use.md)
    * [&.try\(\)](js/ES6/Promise/try.md)
  * Iterator 遍历器
    * [&（遍历器）的概念](js/ES6/Iterator/gainian.md)
    * [默认 & 接口](js/ES6/Iterator/morenbianliqijiekou.md)
    * [调用 & 接口的场合](js/ES6/Iterator/diaoyongbianliqijiekouchanghe.md)
    * [字符串的 & 接口](js/ES6/Iterator/zifuchuanjiekouchanghe.md)
    * [& 接口与 Generator 函数](js/ES6/Iterator/bianliqiheGenerator.md)
    * [遍历器对象的 return\(\)，throw\(\)](js/ES6/Iterator/bianliqideduixiang.md)
    * [for...of 循环](js/ES6/Iterator/for-of.md)
  * async 函数
    * [含义](js/ES6/async/hanyi.md)
    * [基本用法](js/ES6/async/use.md)
    * [语法](js/ES6/async/yufa.md)
    * [async函数原理实现](js/ES6/async/yuanli.md)
    * [与其他异步处理函数比较](js/ES6/async/bijiaoqitayibu.md)
    * [实例:按顺序完成异步操作](js/ES6/async/shili.md)
    * [异步遍历器](js/ES6/async/async-iterator.md)
  * Class 的基本语法
    * [简介](js/ES6/ClassBase/jianjie.md)
    * [严格模式](js/ES6/ClassBase/yangemoshi.md)
    * [constructor](js/ES6/ClassBase/constructor.md)
    * [类的实例对象](js/ES6/ClassBase/shiliduixiang.md)
    * [Class表达式](js/ES6/ClassBase/biaodashi.md)
    * [不存在遍历提升](js/ES6/ClassBase/iterater.md)
    * [私有方法和私有属性](js/ES6/ClassBase/siyou.md)
    * [this的指向](js/ES6/ClassBase/this.md)
    * [name属性](js/ES6/ClassBase/name.md)
    * [&的getter和setter](js/ES6/ClassBase/getersetter.md)
    * [&的Generator方法](js/ES6/ClassBase/generator.md)
    * [&的静态方法](js/ES6/ClassBase/jingtai.md)
    * [&的静态属性和实例属性](js/ES6/ClassBase/jingtaishuxing.md)
    * [new.target属性](js/ES6/ClassBase/newtarget.md)
  * Class 的继承
    * [简介](js/ES6/ClassExtends/jianjie.md)
    * [super](js/ES6/ClassExtends/super.md)
    * [Object.getPrototypeOf](js/ES6/ClassExtends/getPrototypeOf.md)
    * [prototype和proto](js/ES6/ClassExtends/prototypeProto.md)
    * [原生构造函数的继承](js/ES6/ClassExtends/yuanshengjicheng.md)
    * [Mixin模式](js/ES6/ClassExtends/Mixin.md)
  * 修饰器
    * [类的修饰器](js/ES6/Decorator/leidexiushiqi.md)
    * [方法的修饰器](js/ES6/Decorator/funcDecorator.md)
    * [为什么修饰器不能用于函数](js/ES6/Decorator/whyusefunc.md)
    * [core-decorators.js](js/ES6/Decorator/core.md)
    * [使用修饰器实现自动发布事件](js/ES6/Decorator/use.md)
    * [Mixin](js/ES6/Decorator/mixin.md)
    * [Trait](js/ES6/Decorator/trait.md)
    * [babel](js/ES6/Decorator/babel.md)

## MV\*前端框架

* React
  * 基础API
  * React深入实践
  * [React深入指南](mvqian-duan-kuang-jia/reactshen-ru-zhi-nan.md)
    * [fider](MVC/react/plus/fider.md)
    * [Flux架构介绍](MVC/react/plus/flux.md)
    * [React性能调优](MVC/react/plus/tiaoyou.md)
    * [Redux介绍与实战](MVC/react/plus/Redux.md)
    * [GraphQL and Relay](MVC/react/plus/GraphQL.md)
* Vue
  * 基础API
  * Vue深入实践
    * [vuex](MVC/vue/plus/vuex.md)
* Rxjs
  * 基础API
    * [快速上手](MVC/Rx/base/kuaisushangshou.md)

## 后端服务

* HTTP
  * [浏览器⾏为与HTTP协议](HTTP/Unit1/xieyi.md)
  * [什么是HTTP协议](HTTP/Unit1/why.md)
  * [了解TCP/IP协议栈](HTTP/Unit1/xieyizhan.md)
  * [在TCP/IP协议栈中的位置](HTTP/Unit1/xieyiweizhi.md)
  * [HTTP的⼯作过程](HTTP/Unit1/xieyigongzuo.md)
  * [请求与响应](HTTP/Unit1/qingqiuyuxiangying.md)
  * [请求⽅法](HTTP/Unit1/qingqiufangfa.md)
  * [HTTP状态码](HTTP/Unit1/status.md)
  * [常⽤的请求报头](HTTP/Unit1/changyongdeqingqiubaotou.md)
  * [常⽤的响应报头 ](HTTP/Unit1/changyongxiangyingdaotou.md)
  * [实体报头](HTTP/Unit1/shitibaotou.md)
  * [常⽤的实体报头](HTTP/Unit1/changyongshitibaotou.md)
  * [cookies与session](HTTP/Unit1/cookies-session.md)
  * [Cookie使⽤ ](HTTP/Unit1/usecookies.md)
  * [Session的使⽤](HTTP/Unit1/usesession.md)
  * [缓存机制](HTTP/Unit1/huancun.md)
  * [浏览器缓存机制-第⼀次请求](HTTP/Unit1/liulanqidiyiciqingqiu.md)
  * [实体报头-再次请求](HTTP/Unit1/liulanqidierciqingqiu.md)
  * [Etag/If-None-Match策略](HTTP/Unit1/etagcelue.md)
  * [Last-Modiﬁed/If-Modiﬁed-Since策略](HTTP/Unit1/Last-Modiﬁed.md)
  * [HTTP的链路安全](HTTP/Unit1/lianluanquan.md)
  * [下⼀代标准:HTTP2](HTTP/Uni1/http2.md)
  * [HTTP与反向代理](HTTP/Unit1/fanxiangdaili.md)
  * [反向代理的⽤途](HTTP/Unit1/fanxiangdailiyongtu.md)
  * [反向代理做负载均衡](HTTP/Unit1/fanxiangdailifuzaijunheng.md)
  * [让nginx跑起来](HTTP/Unit1/nginxrun.md)

## QA

## 常用的构建工具

## 面试题

* JavaScript基础
  * 拖拽
    * [HTML拖拽](mianshiti/jichu/tuozhuai/html.md)
    * [js拖拽](mianshiti/jichu/tuozhuai/js.md)
  * [js监听对象属性变化](mianshiti/jichu/jiantingduixiangshuxing.md)
  * [mouseover和mouseenter区别](mianshiti/jichu/mouserovermouserenter.md)
  * [once函数](mianshiti/jichu/once.md)
  * [rAF](mianshiti/jichu/raf.md)
  * [promise封装原生ajax](mianshiti/jichu/fengzhuangajax.md)
  * [实现AMD](mianshiti/jichu/shixianAMD.md)
  * [对象深度克隆的简单实现](mianshiti/jichu/chone.md)
  * [懒加载](mianshiti/jichu/lanjiazai.md)
  * [私有变量的访问](mianshiti/jichu/siyoubianliangfangwen.md)
  * [观察者模式](mianshiti/jichu/guanchazhemoshi.md)
  * 防抖节流
    * [简单防抖](mianshiti/jichu/fdjl/jiandanfangdou.md)
    * [封装简单防抖函数](mianshiti/jichu/fdjl/fengzhaungfangdou.md)
    * [简单节流](mianshiti/jichu/fdjl/jieliu.md)
    * [使用rAF](mianshiti/jichu/fdjl/useraf.md)
    * [scroll中优化](mianshiti/jichu/fdjl/scrollyouhua.md)
* 阿里
  * [合并Promise](mianshiti/alibaba/hebingpromise.md)
* 100题直通车
  * JavaScript语言新发展
    * [第1题](mianshiti/ztc/js/101.md)
    * [第2题](mianshiti/ztc/js/102.md)
    * [第3题](mianshiti/ztc/js/103.md)
    * [第4题](mianshiti/ztc/js/104.md)
    * [第5题](mianshiti/ztc/js/105.md)
    * [第6题](mianshiti/ztc/js/106.md)
    * [第7题](mianshiti/ztc/js/107.md)
    * [第8题](mianshiti/ztc/js/108.md)
    * [第9题](mianshiti/ztc/js/109.md)
    * [第10题](mianshiti/ztc/js/110.md)
    * [第11题](mianshiti/ztc/js/111.md)
  * NodeJS 变化
    * [第1题](mianshiti/ztc/node/101.md)
    * [第2题](mianshiti/ztc/node/102.md)
    * [第3题](mianshiti/ztc/node/103.md)
    * [第4题](mianshiti/ztc/node/104.md)
    * [第5题](mianshiti/ztc/node/105.md)
    * [第6题](mianshiti/ztc/node/106.md)
    * [第7题](mianshiti/ztc/node/107.md)
    * [第8题](mianshiti/ztc/node/108.md)
    * [第9题](mianshiti/ztc/node/109.md)
    * [第10题](mianshiti/ztc/node/110.md)
  * 前端工程化与持续构建
    * [第1题](mianshiti/ztc/webpack/101.md)
    * [第2题](mianshiti/ztc/webpack/102.md)
    * [第3题](mianshiti/ztc/webpack/103.md)
    * [第4题](mianshiti/ztc/webpack/104.md)
    * [第5题](mianshiti/ztc/webpack/105.md)
    * [第6题](mianshiti/ztc/webpack/106.md)
    * [第7题](mianshiti/ztc/webpack/107.md)
    * [第8题](mianshiti/ztc/webpack/108.md)
    * [第9题](mianshiti/ztc/webpack/109.md)
    * [第10题](mianshiti/ztc/webpack/110.md)
  * [CSS古话今说与网站重构](mian-shi-ti/cssgu-hua-jin-shuo-yu-wang-zhan-zhong-gou.md)
    * [第1题](mianshiti/ztc/css/101.md)
    * [第2题](mianshiti/ztc/css/102.md)
    * [第3题](mianshiti/ztc/css/103.md)
    * [第4题](mianshiti/ztc/css/104.md)
    * [第5题](mianshiti/ztc/css/105.md)
    * [第6题](mianshiti/ztc/css/106.md)
    * [第7题](mianshiti/ztc/css/107.md)
    * [第8题](mianshiti/ztc/css/108.md)
    * [第9题](mianshiti/ztc/css/109.md)
    * [第10题](mianshiti/ztc/css/110.md)

