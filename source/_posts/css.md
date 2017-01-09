---
title: css相关
---

## css单位



| 属性（Properties）| CSS版本（Version）   | 继承性（Inherit From Parent）  | 简介（Description） |
| ------------- |:-------------:| :-----: | :-----:|
|相对长度单位|
| em      | CSS1      |   无   | 相对于当前对象内文本的字体尺寸 |
| ex      | CSS1      |   无   | 相对于字符“x”的高度。通常为字体高度的一半 |
| ch      | CSS3      |   无   | 通常是数字“0”的宽度 |
| rem     | CSS3      |   无   | 相对于根元素(即html元素)font-size计算值的倍数 |
|视口相对长度单位 Viewport-relative Length Units|
| vw      | CSS1      |   无   | 相对于视口的宽度。视口被均分为100单位的vw |
| vh      | CSS3      |   无   | 相对于视口的高度。视口被均分为100单位的vh |
| vm      | CSS3      |   无   | 对于视口的宽度或高度，总是相对于小的那个。视口的宽度或高度被均分为100单位的vm |
|绝对长度单位|
| cm      | CSS1      |   无   | 长度单位厘米 |
| mm      | CSS3      |   无   | 长度单位毫米 |
| in      | CSS2      |   无   | 长度单位英寸 |
| pt      | CSS1      |   无   | 长度单位点 |
| pc      | CSS1      |   无   | 长度单位派卡 |
| px      | CSS1      |   无   | 长度单位像素 |


<!-- rem	CSS3	无	CSS3 长度单位 rem ，相对于根元素(即html元素)font-size计算值的倍数
vw	CSS3	无	CSS3 长度单位 vw，相对于视口的宽度。视口被均分为100单位的vw
vh	CSS3	无	CSS3 长度单位 vh ，相对于视口的高度。视口被均分为100单位的vh -->


### flex兼容
```css
.flex() {
    display: -webkit-box; 
    display: -moz-box; 
    display:-webkit-flex;
    display: -ms-flexbox;
    display:flex;


    display: -webkit-box;      /* OLD - iOS 6-, Safari 3.1-6 */
    display: -moz-box;         /* OLD - Firefox 19- (buggy but mostly works) */
    display: -ms-flexbox;      /* TWEENER - IE 10 */
    display: -webkit-flex;     /* NEW - Chrome */
    display: flex;             /* NEW, Spec - Opera 12.1, Firefox 20+ */
}

.flex-one{
    -webkit-box-flex: 1;      /* OLD - iOS 6-, Safari 3.1-6 */
    -moz-box-flex: 1;         /* OLD - Firefox 19- */
    width: 20%;               /* For old syntax, otherwise collapses. */
    -webkit-flex: 1;          /* Chrome */
    -ms-flex: 1;              /* IE 10 */
    flex: 1;                  /* NEW, Spec - Opera 12.1, Firefox 20+ */
}

```