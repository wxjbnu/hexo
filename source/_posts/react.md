---
title: react相关
---

## react

https://github.com/zeit/next.js



#### 写法
```javascript

//not recommend
var component = <Component />;
  component.props.foo = x; // 不推荐
  component.props.bar = y; // 不推荐

//ok
var props = {};
  props.foo = x;
  props.bar = y;
  var component = <Component {...props} />;

```


#### 资源
- https://github.com/tsrot/study-notes/blob/master/React%E5%AD%A6%E4%B9%A0%E8%B5%84%E6%BA%90%E6%B1%87%E6%80%BB.md
