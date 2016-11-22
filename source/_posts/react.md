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
- [完整项目](https://github.com/bailicangdu/pxq)
- http://www.open-open.com/lib/view/open1479280199970.html#articleHeader0



#### react-router

```javascript
const RouteConfig = (
    <Router history={history}>
        <Route path="/" component={Roots}>
            <IndexRoute component={index} />//首页
            <Route path="index" component={index} />
            <Route path="helpCenter" getComponent={helpCenter} />//帮助中心
            <Route path="saleRecord" getComponent={saleRecord} />//销售记录
            <Route path="chooseProducts" getComponent={chooseProducts} />//选择商品
            <Route path="allDeposit" getComponent={allDeposit} />//余额
            <Route path="applyDeposit" getComponent={applyDeposit} />//申请提现
            <Route path="applyRecord" getComponent={applyRecord} /> //提现记录
            <Redirect from='*' to='/' />
        </Route>
    </Router>
);
```
