---
title: promise
---

## promise

> JavaScript closures

- http://liubin.org/promises-book/#what-is-promise


```
// promise 连式结构
function asy() {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            resolve('Async Hello world');
        }, 16);
    });
}
asy().then((res)=>{
     return new Promise(function (resolve, reject) {
        setTimeout(function () {
            resolve('first : '+res);
        }, 1000);
    });
}).then((res)=>{
     return new Promise(function (resolve, reject) {
        setTimeout(function () {
            resolve('second: '+res);
        }, 2000);
    });
}).then((res)=>{console.log(res)})
```
