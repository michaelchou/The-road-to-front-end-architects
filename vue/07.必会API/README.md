# Vue.set/vm.$set

向响应式对象中添加一个属性，并确保这个新属性同样是响应式的，且触发视图更新

```javascript
Vue.set(target:object|Array, propertyName/index, value)
```

# Vue.delete/vm.$delete

删除对象的属性，如果对象是响应式的，确保删除能触发更新视图

```javascript
Vue.delete(target, propertyName / index);
```

# vm.$on

监听当前实例上的自定义事件。事件可以由 vm.$emit 触发。回调函数会接收所有传入事件触发函数的额外参数。

```javascript
vm.$on('test', function (msg) {
  console.log(msg);
});
vm.$emit('test', 'hi');
```

## 典型应用：事件总线

通过在 Vue 原型上添加一个 Vue 实例作为事件总线，实现组件间相互通信，而且不受组件间关系的影响

```javascript
// 这样做可以在任意组件中使用this.$bus访问到该Vue实例
Vue.prototype.$bus = new Vue();
```

# vm.$once

监听一个自定义事件，但是只触发一次。一旦触发之后，监听器就会被移除

```javascript
vm.$once('test', (msg) => {
  console.log(msg);
});
```

# vm.$off

移除自定义监听事件

- 如果没有提供参数，则移除所有的事件监听器；
- 如果只提供了事件，则移除该事件所有的监听器；
- 如果同时提供了事件和回调，则只移除这个回调的监听器

```javascript
// 移除所有的事件监听器
vm.$off();
// 移除该事件的所有监听器
vm.$off('test');
// 只移除这个回调的监听器
vm.$off('test', callback);
```

# 组件和元素引用

## ref 和 vm.$refs

ref 被用来给元素或子组件注册引用信息。引用信息将会注册在父组件的$refs 对象上。如果**在普通的 DOM 元素上使用，引用指向的就是 DOM 元素**;如果**用在子组件上，引用就指向组件实例**

- ref 是作为渲染结果被创建的，在初始渲染时不能访问他们
- $refs 不是响应式的，不要试图用它在模板中做数据绑定
- 当 v-for 用于元素或组件时，引用信息将是包含 DOM 节点或组件实例的数组
