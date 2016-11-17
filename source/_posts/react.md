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
