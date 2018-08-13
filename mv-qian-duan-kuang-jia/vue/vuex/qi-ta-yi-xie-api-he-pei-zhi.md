# 其他一些API和配置

## plugins

subscribeAction和subscribe

```text
plugins: [
      (store) => {
        console.log('store plugins')
        store.subscribeAction((action, state) => {
          console.log(action.type)
          console.log(action.payload)
        })
      },
      (store)=>{
        store.subscribe((mutation,state)=>{
          console.log(mutation.type)
          console.log(mutation.payload)
        })
      }
    ],
```

## watch

```text
// 接受两个函数钩子参数:在监听state的时候,返回值作为第二个函数的参数
// store.watch((state)=>state.count+1,(newCount)=>{console.log(newCount)})
```

