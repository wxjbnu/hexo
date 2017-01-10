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