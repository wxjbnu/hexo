---
title: mozilla之深入学习es6
---


# 中文版
[中文版链接](http://www.csdn.net/tag/%E6%8E%A2%E7%A7%98es6/news)

## Modules


[链接](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/)

### proxy
- http://es6.ruanyifeng.com/#docs/proxy
```javascript
var proxy = new Proxy({}, {
  get: function(target, property,val) {
    
  },
  set: function(target, property,val){
    target[property] = val
    console.log(target,property,val)
  }
});
```


###

```javascript
myname = {name:'www'}
Object.defineProperty(myname, 'key', {value:123})
```