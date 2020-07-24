# javascript-spec


## 分号

**1**、 在以

```
[
(
+
-
/
`
*
```

为行首字符的前面加分号

[JavaScript 语句后应该加分号么？](https://www.zhihu.com/question/20298345)


## 变量命名

不使用类型前缀命名

```js
/*
 * bad
 */
var eBtn = document.getElementById('btn') // element
var aQueue = ['1','2'] // array
var sName = 'nimo' // string
var iCount = 2 // integer
var oUser = {name: 'nimo'} // object
var flValue = 1.223123 // float
var reName = /nimo/ // regexp
var fnCall = function () {/*...*/} // function
```

**在必要时通过后缀标示或通过单词含义去表达类型**

> 让维护者通过单词就能知道类型是什么

```js
/*
 * array
 */
var id = 'a123'
var idArray = ['a123', 'b123']
// 尽量避免使用 var id= 'a123,b123' 需要获取数据时通过 idArray.join(',') 获取

// queue 已经能够表明这是一个数组
var queue = ['1', '2']

/*
 * element
 */
var btn = document.getElementById('btn') // btn 一般都是 element不需要做标示

/*
 * object
 */
var userData = {name: 'nimo'}
var actionDict = {'delete': '删除', 'edit': '编辑'}
var cacheMap = {}; cacheMap[url] = {/*...*/}

/*
 * number
 */
var count = 1 // count 肯定是数字类型
var age = 10 // iAge 是多此一举
var price = 10.5 // 可以不命名成 flPrice

/*
 * function
 */

// 看到动词就知道是个函数
var changeName = function(){}
var getData = function () {}
var setData = function () {}
```

### 变量声明

尽量使用 `const` ，其次 `let` 。 使用 `const` 能有效避免错误的重新赋值变量。

### 原则

只在必要的地方注释，尽量通过变量名和语句替代注释。例如：

```js
// bad
if (age < 18) {
    console.log('Close your eyes')
}
// good
var isKid = age < 18
if (isKid) {
    console.log('Close your eyes')
}
```

必要时直接通过文档的方式写出程序流程和设计方式
