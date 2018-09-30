---
title: Vue.js读书笔记
1.是一套用于构建用户界面的渐进式框架。
2.<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
 <!-- 生产环境版本，优化了尺寸和速度 -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
3.Vue.js的核心是一个允许采用简洁的模板语法来声明式地将数据渲染进DOM的系统：
4.指令 v-xxx
5.v-bind缩写
    <!-- 完整语法 -->
<a v-bind:href="url">...</a>

<!-- 缩写 -->
<a :href="url">...</a>
6.v-on缩写
    <!-- 完整语法 -->
<a v-on:click="doSomething">...</a>

<!-- 缩写 -->
<a @click="doSomething">...</a>
7.计算属性和侦听器
7.1 methods 每次都调用函数； computed 可以进行缓存。
7.2侦听器 watch         虽然计算属性在大多数情况下更合适，但有时也需要一个自定义的侦听器。这就是为什么 Vue 通过 watch 选项提供了一个更通用的方法，来响应数据的变化。当需要在数据变化时执行异步或开销较大的操作时，这个方式是最有用的。
8.Class与Style绑定
9.条件渲染  v-if   v-else
    <template v-if="ok">
  <h1>Title</h1>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
   </template>
   
   v-else-if 
   9.1用key管理可复用的元素  
   9.2 v-show     不同的是带有 v-show 的元素始终会被渲染并保留在 DOM 中。                                v-show 只是简单地切换元素的 CSS 属性 display。
   9.3   一般来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好。
   9.4 当 v-if 与 v-for 一起使用时，v-for 具有比 v-if 更高的优先级。
 10. 列表渲染  
   10.1 v-for   我们用 v-for 指令根据一组数组的选项列表进行渲染。v-for 指令需要使用 item in items 形式的特殊语法，items 是源数据数组并且 item 是数组元素迭代的别名。
   10.2  建议尽可能在使用 v-for 时提供 key，除非遍历输出的 DOM 内容非常简单，或者是刻意依赖默认行为以获取性能上的提升。
            因为它是 Vue 识别节点的一个通用机制，key 并不与 v-for 特别关联，key 还具有其他用途，
 11.事件处理
   11.1 监听事件    可以用 v-on 指令监听 DOM 事件，并在触发时运行一些 JavaScript 代码。
  12 表单输入绑定
   12.1 用 v-model 指令在表单 <input>、<textarea> 及 <select> 元素上创建双向数据绑定。
 13.组件
       组件是可复用的 Vue 实例，且带有一个名字：
	   一个组件的 data 选项必须是一个函数
	   13.1全局注册 Vue.component
	   13.2 通过prop 向子组件传递数据          Prop 是你可以在组件上注册的一些自定义特性。当一个值传递给一个 prop 特性的时候，它就变成了那个组件实例的一个属性。为了给博文组件传递一个标题，我们可以用一个 props 选项将其包含在该组件可接受的 prop 列表中：
	   13.3 一个组件默认可以拥有任意数量的 prop，任何值都可以传递给任何 prop。
	   13.4 所有的 prop 都使得其父子 prop 之间形成了一个单向下行绑定：父级 prop 的更新会向下流动到子组件中，但是反过来则不行。这样会防止从子组件意外改变父级组件的状态，从而导致你的应用的数据流向难以理解。
	   13.5 如果你不希望组件的根元素继承特性，你可以设置在组件的选项中设置 inheritAttrs: false  
	   14.