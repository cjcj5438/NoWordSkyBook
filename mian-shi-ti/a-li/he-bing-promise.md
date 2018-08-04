# 合并Promise

## 合并Promise

```javascript

    // 在mergePromise 每部写出代码
    // 打印结果为:1 2  3 done [1,2,3]
    const timout = ms => new Promise(resolve => {
        setTimeout(() => {
            resolve()
        }, ms)
    })
    const ajax1 = () => timout(2000).then(() => {
        console.log("1");
        return 1
    })
    const ajax2 = () => timout(1000).then(() => {
        console.log("2");
        return 2
    })
    const ajax3 = () => timout(2000).then(() => {
        console.log("3");
        return 3
    })
    const mergePromise = (ajaxArray) => {
        //todo..
    }
    mergePromise([ajax1, ajax2, ajax3]).then(data => {
        console.log("done");
        console.log(data)
    })

```

## 方法一

```javascript
const mergePromise = (ajaxArray) => {
   return new Promise((r) => {
        const arr = [];
        (async () => {
            for (let item of ajaxArray) {
                arr.push(await item())
            }
            r(arr)
        })()
    })
}
```

## 方法二

```javascript
const mergePromise = (ajaxArray) => {
    return ajaxArray.reduce((preajax, ajax) => {
         return new Promise(resolve => {
             if (typeof preajax === "function") preajax = preajax();
             preajax.then(predate => {
                 ajax().then(data => {
                     resolve([].concat(predate).concat(data))
                 })
             })
         })
     })
}
```

## ~~方法三~~

```javascript
const mergePromise = (ajaxArray) => {
  var arr = [],
            ajaxLength = ajaxArray.length;
        for (var i = 0; i < ajaxLength; i++) {
            ajaxArray[i].next = ajaxArray[i + 1];
        }

        function todo(item) {
            item().then(data => {
                arr.push(data);
                var _next = item.next;
                _next && todo(_next)
            });
        }

        todo.then = (data) => {
            ajaxArray[ajaxLength - 1].next = () =>
                timout(0).then(() => {
                    data(arr)
                })

            todo(ajaxArray[0])
        }
        return todo

}
```

