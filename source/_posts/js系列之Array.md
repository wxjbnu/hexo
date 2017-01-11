---
title: js系列之Array
---

## js系列之Array

### 方法
- Array.apply(null,{length:10}),新建一个长度10的数组

```javascript
//Array.apply(null, {length: 10})和Array(10)有什么区别?
Array.apply(null, {length: 10})//[undefined,undefined,undefined...]
Array(10)//[undefined*10];
```




### 循环

```javascript
var myArray = [];

//最早的循环,里面可以用break中断，但是不能return
for (var index = 0; index < myArray.length; index++) {   
    console.log(myArray[index]);   
}

//es5新加,可以用return,但是只能跳过当前,不能用break
myArray.forEach(function (value) {
    console.log(value);  
});

//可以用break,但是不能用return,也可以遍历对象
for (var index in myArray) {     // don't actually do this   
    if(myArray[index]=='c'){
       break
    }
    console.log(myArray[index]);   
}

//支持break、continue
//能用在Map和Set对象上，也能用在string
for (var value of myArray) {
    console.log(value);   
}
```