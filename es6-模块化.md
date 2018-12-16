# 模块化

## 导出默认模块
```js
/* myModule.js */
export default function () {
    return 'boo!'
}
/* end myModule.js */

// 引入默认模块只能像下面这样写
import myModule from 'myModule';
console.log(myModule()); // boo!
```

## 导出有名字的成员模块
```js
/* myModule.js */
export const greeting = 'hello';
/* end myModule.js */

import { greeting } from 'myModule';
console.log(greeting); // hello
```

## 将有名字的成员模块重命名
```js
/* myModule.js */
export const pi = 3.14;
/* end myModule.js */

import { pi as pie } from 'myModule';
console.log(pie); // 3.14
```

## 导出多个有名字的成员模块
```js
/* myModule.js */
export const greeting = 'hello';
export const sendOff = 'cya';
export function greet(name) {
    return 'greeting' + ' ' + name;
};
/* end myModule.js */

import { greet, greeting, sendOff } from 'myModule';
console.log(greeting); // hello
console.log(sendOff); // cya
console.log(greet('Matt')); // hello
```

## 多个有名字的成员模块，作为一个命名空间被引入
```js
/* myModule.js */
export const greeting = 'hello';
export const sendOff = 'cya';
export function greet(name) {
    return "greeting" + ' ' + name;
};
/* end myModule.js */

import { * as greetingStuff } from 'myModule';
console.log(greetingStuff.greeting); // hello
console.log(greetingStuff.sendOff); // cya
console.log(greetingStuff.greet('Matt')); // hello
```

## 默认的和带名字的成员模块一起被导出
```js
/* myModule.js */
export const greeting = 'hello';
export const sendOff = 'cya';
export default function greet(name) {
    return "greeting" + ' ' + name;
};
/* end myModule.js */

import myModule, { sendOff } from 'myModule';
console.log(sendOff); // cya
console.log(myModule('Matt')); // hello
```