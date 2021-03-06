# 迭代器模式
### 定义：
提供一种方法顺序访问一个聚合对象中的各个元素，而又不暴露其内部的表示。

### 我的理解
迭代器模式，封装了集合具体的数据结构，统一了遍历的返回对象。 这样，对于客户不用关心你具体的集合组织形式，对于任何的集合
都同样地对待。

### 次序问题
使用迭代器，意味着没有次序。 只是取出所有元素，并没有表示取出元素的先后，就代表元素的大小次序。
所以，除非迭代器有对某个集合元件有特殊说明，否则不该对元素的大小做出假设。

### 设计原则
```sh
单一责任： 一个类应该只有一个引起变化的原因。
```
类的每一个责任都有要改变的潜在区域。超过一个责任，意味着超过一个的改变区域。
这个原则告诉我们， 只将一个责任指派给一个类。

这个和内聚的概念很相似： 当一个模块或者类被设计成只支持一组相关的功能的时候， 我们说其具有高内聚。
反子， 当设计被支持成一组不相关的功能的时候，我们说它具有低内聚。

然而，区分设计中的责任，是最困难的事情。我们应该随着系统的成长，随时做观察。

### 相关的类
Collection

### 备注
从Java 5开始，我们的foreach甚至帮助我们避免了迭代器！