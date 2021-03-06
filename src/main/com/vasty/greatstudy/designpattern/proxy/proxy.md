# 代理模式

### 定义
代理模式为另一个对象提供一个替身或占位符以控制对这个对象的访问。
（被代理的对象可以是远程的对象， 创建开销大的对象或者需要安全控制的对象等等）

### 具体情况的一些例子
代理有很多变体，这里列举一些：
- 远程代理   控制访问远程对象。
- 虚拟代理   控制访问创建开销大的资源。
- 保护代理   基于权限控制对资源的访问。
- 防火墙代理 控制网络资源的访问， 保护主题免于“坏客户”的侵害。
- 智能引用代理 当主题被引用时，进行额外的动作，例如计算一个对象被引用的次数。
- 缓存代理   为开销大的运算结果提供暂时的存储，它也允许多个客户共享结果，以减少网络延时。
- 同步代理   为多线程的情况下，为主题提供安全的访问。
- 复杂隐藏代理 用来隐藏一个类的复杂集合的复杂度，并进行访问控制。 有时候也称为外观代理。 复杂隐藏代理和外观模式是不一样的，因为代理控制访问，而外观模式只提供了一组接口。
- 写入时复制代理 用来控制对象的复制，方法是延迟对象的复制，知道客户真的需要为止。 这是虚拟代理的变体。

### 类图见eap

### 虚拟代理的用法
例子： 建立一个应用程序， 用来展现最喜欢的CD封面。但是CD封面要从网络上下， 可以不直接访问加载控件，而使用代理， 在没有下好
的情况下，由代理绘制加载， 而下好后，交给控件，做显示。


### 保护代理的用法
类图见eap（动态代理）
例子： 一个程序，只能自己修改自己的资料，而不能让别人修改这个资料。同时， 只能让别人给你评价，而不能自己修改自己的评价。
在这个例子中，需要两个动态代理，一个代理对自己的访问，一个代理对他人的访问。 这样，在动态代理技术中，应该是两个InvocationHandler.

### 动态代理Tips
- 动态代理 是指 运行时才将它的类创建出来。 代码开始执行的时候还没有Proxy类， 它是根据需要从你传入的接口集创建的。
- Proxy方法有一个静态方法，叫做isProxyClass()，可以判断是否为动态代理类。
- 对于传入newProxyInstance()这个方法中的接口类型是有限制的。 这个数组中只能有接口，不能有类，如果接口不是public那么必须在同一个package。 不同的接口内，不能有名称和
参数完全一样的方法。 还有其他的一些细微的限制， 需要去看JavaDoc。


