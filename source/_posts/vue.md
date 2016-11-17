
---
title: vue的各种‘坑’
---




#### 数组更新检测
- push()
- pop()
- shift()
- unshift()
- splice()
- sort()
- reverse()

> Vue 不能检测以下变动的数组:
> 当你直接设置一个项的索引时，例如： vm.items[indexOfItem] = newValue
当你修改数组的长度时，例如： vm.items.length = newLength
> 需要用代替
`// Vue.set
Vue.set(example1.items, indexOfItem, newValue)
// Array.prototype.splice
example1.items.splice(indexOfItem, 1, newValue)

example1.items.splice(newLength)
`
