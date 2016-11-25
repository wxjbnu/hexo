---
title: 资源收集
---

## 资源收集

[Javascript的继承与多态](http://www.jianshu.com/p/5cb692658704)



```javascript
//es5继承
//构造函数
function Person(name){
 this.name=name||"default name"; //1
 this.className="person"
}
Person.prototype.getName = function(){
 console.log(this.name)
}
function Man(name){
  Person.apply(this,arguments)
}
//继承原型
Man.prototype = new Person();
var man1=new Man("Davin");
```
