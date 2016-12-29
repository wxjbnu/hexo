---
title: js设计模式
---

- 单例模式
```javascript
var singleton = function( fn ){
    var result;
    return function(){
        return result || ( result = fn .apply( this, arguments ) );
    }
}
//调用
var createMask = singleton( function(){
    return document.body.appendChild( document.createElement('div') );
})
```