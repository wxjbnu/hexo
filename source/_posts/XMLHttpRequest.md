---
title: XMLHttpRequest
---

### vue-resource单独出来导出情况
```javascript
this.$http.post(ourl,{})
.then((res)=>{
    console.log(res.data)
    try{
        if(res.data.hasOwnProperty('status')){
        alert(res.data.message)
        }else{
        window.open(ourl)
        }
    }catch(err){
        console.log(err)
    }
});
```

## 类型

- (文档)[http://www.zhangxinxu.com/wordpress/2013/10/understand-domstring-document-formdata-blob-file-arraybuffer/]
- DOMString、Document、FormData、Blob、File、ArrayBuffer这些类型


### blob类型
- https://developer.mozilla.org/zh-CN/docs/Web/API/Blob