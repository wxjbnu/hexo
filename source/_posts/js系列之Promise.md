---
title: js系列之Promise
---

## js系列之Promise

### 方法

```javascript
var pf = function(num){
   return new Promise((resolve, reject) => {
       if(num%2==0){
          return reject(1);
       }else{
         return resolve(0);
       }
   })
}
//执行
pf(112)
.then((e)=>{return e},(err)=>{return 999})
.then((e)=>{console.log(e)})
```