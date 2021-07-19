# Vue 组件化的理解

组件化是 Vue 的精髓，Vue 应用就是一个个组件构成。Vue 的组件化涉及到的内容非常多，当面试时被问到：谈一下你对 Vue 组件化的理解。这时候有可能无从下手，可以从以下几点进行阐述：

## 定义：组件是可复用的 Vue 实例，准确的讲，它们应该是 VueComponent 的实例，继承自 Vue。

## 有点：从上面案例可以看出组件化可以增加代码的复用性、可维护性和可测试性。

## 使用场景：什么时候使用组件？以下分类可作为参考：

1、通用组件：实现最基本的功能，具有通用性、复用性。例如按钮组件、输入框组件、布局组件等。
2、业务组件：他们完成具体业务，具有一定的复用性，例如登陆组件、轮播图组件。
3、页面组件：组织应用各部分独立内容，需要时在不同页面组件间切换，例如列表页、详情页组件。

## 如何使用组件

1、定义：Vue.component,components 选项
2、分类：有状态组件，functional，abstract
3、通信：props,$emit/$on,provide/inject,$children/$parent/$root/$attrs/$listeners
4、内容分发：slot，template，v-slot
5、使用及优化：动态组件、异步组件，keep-alive

## 组件的本质

vue 中的组件经历如下过程：
组件配置->VueComponent 实例->render()->Virtual Dom->DOM
所以组件的本质产生虚拟 DOM
