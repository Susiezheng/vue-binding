# vue-binding
简单的vue双向绑定实现


#### 在 new SelfVue 后会调用 init 函数初始化，在这个过程中 DATA 通过 observer 转换成 getter 和 setter 的形式对数据追踪变化，当追踪对象被读取时执行 getter,被赋值时执行 setter。
#### 当外界通过 watcher 读取数据时，会触发 getter 从而将 watcher 添加到依赖中。当修改对象的值，会触发对应的 setter。setter 会通知之前依赖收集到的 Dep 中的每一个 watcher，告诉它我被改变了，需要重新渲染页面，这时候 watcher 会开始调用 update 来更新视图。