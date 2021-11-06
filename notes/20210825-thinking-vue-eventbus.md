# 在 Vue 中使用 EventBus 的思考

#vue #eventbus #convention #recommendations

在现代前端框架（Angular、React、Vue），组件通信是十分重要的内容。

## 前端组件化与面向对象编程（OOP）思想

我们可以从面向对象编程OOP passing message 的角度，来思考前端组件的消息通信。前端组件是类（class） render 后是对象（object）。

## Vue 中通过组件实例调用组件的方法

在 Vue 中，我们可以通过对象调用方法实现 `passing message` 。比如：
```javascript
this.$parent.methodA()
this.$refs.['componetName'].methodA()
```
调用一个对象的方法，来传递消息。这是一种清楚的传递消息的方式，谁负责发送消息、谁负责接受消息，一目了然。但因为Vue 的局限， 兄弟组件难以通过这种方式传递消息。

使用`EventBus` 中 `emit on` 的模式做组件通信。某些程度上就像是在使用 `全局状态数据` 。使用 EventBus 在发布时不清楚有哪些地方订阅，如果没什么最佳实践，只能通过注释的方式写。
我想到一种写法：

```javascript
// A Component
created () {
    EventBus.$on('src/views/something:getSomethingList', () => { this.getSomethingList() });
}
beforeDestroy() {
    EventBus.$off('src/views/something:getSomethingList')
}
// B Component
EventBus.$emit('src/views/something:getSomethingList')
```

## 使用建议

核心思想是： **使用 EventBus 作为暴露组件方法的技巧**

- 仅在单实例组件中使用 EventBus
- 将组件路径作为事件注册的名称，保证唯一性。
- created 时创建方法（`on`）、 beforeDestroy销毁方法（`off`），缺一不可。
- 在 methods 中调用方法 （`emit`），不再生命周期钩子中调用方法。

## 总结与思考

对复杂度的控制，对代码可读性的追求，永无止境，做工程，要有持续迭代优化的追求，能优化一点是一点。不断改进，让代码变得更健壮、更加容易阅读。

每一种技术都有适用范围。在合适的场景下选择合适的技术。可以利用 Vuex 做全局的 组件通信。但如果只是在某一个页面模块局部，用 EventBus 会方便一些、不过要注意使用的方式。 
