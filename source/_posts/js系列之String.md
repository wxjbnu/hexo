---
title: js系列之String
---

## js系列之String

### 方法
- String.fromCharCode  转换为字符

```javascript
for(let i=-58;i<26;i++){
    console.log(String.fromCharCode(0x60+i))
}
```