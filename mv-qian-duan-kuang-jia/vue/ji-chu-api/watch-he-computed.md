# watch和computed

```javascript
import Vue from 'vue'

new Vue({
  el: '#root',
  template: `
    <div>
      <p>Name: {{name}}</p>
      <p>Name: {{getName()}}</p>
      <p>Number: {{number}}</p>
      <p>FullName: {{fullName}}</p>
      <p><input type="text" v-model="number"></p>
      <p>FirstName: <input type="text" v-model="firstName"></p>
      <p>LastName: <input type="text" v-model="lastName"></p>
      <p>Name: <input type="text" v-model="name"></p>
      <p>Obj.a: <input type="text" v-model="obj.a"></p>
    </div>
  `,
  data: {
    firstName: 'Jokcy',
    lastName: 'Lou',
    number: 0,
    fullName: '',
    obj: {
      a: 0
    }
  },
  /*可以对数据做缓存,如果里面依赖的值在变化. 他会重新计算一次然后在缓存起来
  * 而如果是数据写在methods里面.每次操作数据都会触发methods里面的函数执行
  * 那么computed 我们一般用在什么地方呢? 其实就是object.defindporotype方法
  * 就是我们拿到这部分数据不是正在想要去显示的数据,我们要通过计算,然后处理 显示
  * 当然也可以使用设置操作 get 和set 但是这样不建议用 合并容易 拆开合并很容易出错*/
  computed: {
    // name(){
    //   console.log('new name')
    //   return `${this.firstName} ${this.lastName}`
    // }
    name: {
      get () {
        console.log('new name')
        return `${this.firstName} ${this.lastName}`
      },
      set (name) {
        const names = name.split(' ')
        this.firstName = names[0]
        this.lastName = names[1]
      }
    }
  },
  /*使用场景.并不是根据firstName 或者是 lastName 我去监听这两个东西.就要
  * 写两个handle,写的代码也要多一倍 使用场景比如说们监听到某个值变化.然后发送一个请求
  * 抽象来说*/
  watch: {
/*    以前很多同学是这样写的.但是只有值改变之后才会触发监听,
    我们可以使用 handler 加 immdeiate 来使方法声明时就触发*/
    firstName(newName,oldName){
      this.fullName=newName+ " "+ this.lastName
    },

    'obj.a': {
      handler () {
        console.log('obj.a changed')
        this.obj.a += 1
      },
      immediate: true
      // deep 可以深入观察  这样很耗性能:ojb 可以改成 "obj.a"  换成字符串,这样可以降低性消耗
      // deep: true
    }
  },
  methods: {
    getName () {
      console.log('getName invoked')
      return `${this.firstName} ${this.lastName}`
    }
  }
})

//这里要注意的一点. 不要用computed 和 watch 去修改值. 只能是生成一个新的值,
//
// 会无限触发watch 事件

// 功能去监听然后生成一个新的值, 而不是监听了之后而去改某一个值

```

