## ⭐Promise

**Promise** 是异步编程的一种解决方案 。

**Promise** 对象用于表示一个异步操作的最终状态（完成或失败），以及其返回的值 

### 语法

```js
// resolve函数的作用是，将Promise对象的状态从“未完成”变为“成功”（即从 pending 变为 fulfilled），在异步操作成功时调用，并将异步操作的结果，作为参数传递出去
// reject函数的作用是，将Promise对象的状态从“未完成”变为“失败”（即从 pending 变为 rejected），在异步操作失败时调用，并将异步操作报出的错误，作为参数传递出去。
new Promise((resolve, reject) => {...})
```

一个 `Promise`有以下几种状态:

- *pending*: 初始状态，既不是成功，也不是失败状态。
- *fulfilled*: 意味着操作成功完成。
- *rejected*: 意味着操作失败。

Promise对象的状态改变，只能有两种情况：

- 从pending变为fulfilled
- 从pending变为rejected



```js

let promise = new Promise((resolve, reject) => {
  // 一个promise对象只能有一个状态，不能一会儿这个状态，一会儿那个状态
  setTimeout(() => {
    resolve('user对象')
  }, 1000);

  setTimeout(() => {
    reject('一些错误信息')
  }, 500);
})

promise
  .then((data) => {
    console.log(data)
  })
  .catch((err) => {
    console.log(err)
  })


```

