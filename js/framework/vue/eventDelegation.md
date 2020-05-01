# Vue 中是否有必要使用事件委托
## 事件委托有两个主要优点：
1. 少添加事件监听可以方便的删除事件监听，释放内存。但是释放事件监听的事情[Vue已经为你做到了](https://cn.vuejs.org/v2/guide/events.html)。
   ![img](./assets/event.png)
   
2. 另一个是性能/内存。由于v-vor循环中的每个单击侦听器都将使用相同的回调，因此除非你有成百上千的行或者确实遇到性能瓶颈，可以考虑不使用事件代理。

## 结论
最后，你可以通过向父元素ul添加@click侦听器来轻松实现事件委托。但是随后，你必须使用event.target 来判断点击的是哪个子元素。因此，只有在你真正发现性能问题而没有使用事件委托的情况下，才使用它。

# 参考
1. [Vue列表 — 事件委托](https://segmentfault.com/a/1190000011698763)