---
title: js库、框架
---

## js库、框架
- [Neat.js](http://neat.dtworkroom.com/)
- [cyclejs](https://cycle.js.org/)
- [ractivejs](http://www.ractivejs.org/)
- [meteor-app](https://www.meteor.com/) [中文](http://zh.discovermeteor.com/)
- [Velocity](http://velocityjs.org/)动画js库
- [跑性能](https://github.com/krausest/js-framework-benchmark)


#### 随意写的函数

```javascript
//判断是否为质数，大于4开始
function iszhi(num){
     console.log(num)
    if(num<=4) return '太小'
    for(let i=2;i<num/2;i++){
        if(num%i==0){
           console.log(i,num/i)
           return '不是质数'
        }
    }
    return '是质数'
}

```