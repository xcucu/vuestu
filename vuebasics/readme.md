# vue基础部分知识

[速度慢可以来我的博客](https://www.lookroot.cn/course/vuebasics/)

## 目录

- [vuejs的结构和生命周期](https://github.com/lookroot/vuestu/tree/master/vuebasics/v1starter)
- [vue数据处理和渲染](https://github.com/lookroot/vuestu/tree/master/vuebasics/v2data)
- [vue常用指令和事件](https://github.com/lookroot/vuestu/tree/master/vuebasics/v3event)
- [vue组件](https://github.com/lookroot/vuestu/tree/master/vuebasics/v5components)
- [vue过滤器和自定义指令](https://github.com/lookroot/vuestu/tree/master/vuebasics/v6filtersanddirective)
- [vue路由](https://github.com/lookroot/vuestu/tree/master/vuebasics/v7router)
- [vue单文件开发](https://github.com/lookroot/vuestu/tree/master/vuebasics/v8singlevuepage)


## vue使用场景

大家可能都会有这种疑惑啊，到处都在讲学习vue，那么学了到底有啥用啊

这一节就来讲一讲vue的使用场景

### 复杂的表单应用用来构建后台管理系统

我们在一些网站的管理后台，在填入一些表单的时候，非常多的字段，而且一些字段比较复杂，比如多级联动啊

还有一些复杂的表格展示利用vue的数据绑定就非常的方便

### 大量数据渲染的页面

比如我们刚刚消息中心这个界面，下面的数据是非常长的，如果传统的操作dom循环的非常大的性能消耗造成页面卡顿，体验非常不好

![vue教程-lookroot](https://img.lookroot.cn/blog/202003/25/011348-293552.png)

### 移动端开发利器

- 小程序还有一些跨平台App框架比如uniapp weex都是使用vue或者类vue语法

- 很多网站的移动端页面用起来像真的app一样，这种就非常适合使用vue进行开发

![vue教程-lookroot](https://img.lookroot.cn/blog/202005/03/223552-176484.png)

![Vue教程-lookroot](https://img.lookroot.cn/blog/202003/25/112003-968167.png)

## 什么是mvvm

> Model-View-ViewModel

很多初学者就对这个比较模糊，其实我这里讲了你也不一定能理解，这个东西还是需要实践才能体会

我尽量讲的通俗一点

首先还是这张图，大家可能都看过了，这里我们举一个例子结合图来说明

![Snipaste_2020-03-23_22-11-13](https://img.lookroot.cn/blog/202003/25/012333-604474.jpeg)

比如我们的电脑，显示器等同于(view视图层),硬盘等同于(model数据层),那么电脑显示器怎么去展示硬盘里面的一个文本，还有我们在显示器输入的内容它又怎么去存储到硬盘的呢，这就得通过操作系统等同于(ViewModel视图绑定)，他就完成了数据绑定和dom监听（收集操作和数据）

### 优点

视图 UI 和业务逻辑分离了，可以专注的去做各自的事情，这里可能大家就模糊了

我举个例子，比如一个购物车，上面是商品列表，下面是总的商品数量和金额的计算，你点击上面商品的增加数量或者删除商品，下面的数据要跟着变化

![vue教程-lookroot](https://img.lookroot.cn/blog/202003/25/134936-828512.png)

如果你使用jquery这类传统开发会怎么做 触发点击事件->获取dom数据->处理数据->更新dom，那么这个就是一个取出数据又填充数据的过程

mvvm的开发怎样做的呢，对应的位置绑定点击事件->触发事件处理数据->自动更新

在后面学习中大家就能够理解了

## 什么是spa单页面web应用

> 单页Web应用（single page web application，SPA），就是只有一张Web页面的应用，是加载单个HTML 页面并在用户与应用程序交互时动态更新该页面的Web应用程序。

这样讲就太官方了其实不好理解，那我就用一点通俗的话来讲

我们打开bilibili点击导航栏的排行选项，我们发现浏览器进行了跳转到达了另外一个页面实现了页面切换，这样的效果还包括比如`404.html` 每一个路径对应一个具体的页面

![vue教程-lookroot](https://img.lookroot.cn/blog/202003/25/005615-227748.gif)


然后我们来看哔哩哔哩的另外一个界面，在这个界面大家可以发现，无论我怎么点击 页面也切换了路径也变化了，但是浏览器并没有重新加载一个新的页面

![vue教程-lookroot](https://img.lookroot.cn/blog/202003/25/005916-522475.gif)

后者就是单页面web应用，好处大家是肉眼可见的，速度快，操作体验好

那么是怎样实现的呢 以本节的`vue`举例，刚刚上图我们可以发现其实浏览器路径是变化了的，这个就是**路由**切换（通过hash或者pushsate），可以理解为虚拟路径，通过监控虚拟路径的变化，切换不同组件的显示，就达到了切换页面的效果

具体这个组件和路由会在后面讲到