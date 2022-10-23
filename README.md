# front-end-interview-notes-formyself
准备前端面试中发现的不懂的基础知识点
答案为整理总结而得

1.Q：双向绑定的原理？
  A：Vue采用数据劫持结合发布者、订阅者模式的方式，通过object.defineproperty来劫持各个属性的setter，getter，在数据变动时发布消息给订阅者，触发相应的监听回调，以此实现双向绑定
2.Q：v-for中key的原理、不用key与用key的区别
  A：key的原理：key给每一个vnode的唯一id，是diff的一种优化策略，可以根据key更准确 更快的找到对应vnode节点
    不用key： vue会采用就地复用原则，最小化element的移动
    使用key：根据key顺序记录element， 不再出现的element会remove或destoryed

3.Q:keep-alive的理解
  A：keep-alive 是 Vue 的内置组件，在组件切换过程中将状态保留在内存中，等再次访问的时候，还保持着离开之前的所有状态，而不是重新初始化。也就是所谓的组件缓存。
我们知道，使用路由vue-router切换组件的时候是不保存状态的，它进行$router.push()或$router.replace()的时候，旧组件会被销毁，新组件会被新建，然后走一遍完整的生命周期。所以缓存经常与router-view一起出现。
     使用场景有多级表单选择时，使用keepalive缓存用户的选择，使其后退时仍记住选项。
