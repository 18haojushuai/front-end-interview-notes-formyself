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
     
4.Q：diff算法？
  A：diff算法是一种通过同层的树节点进行比较的高效算法
     其有两个特点：

     比较只会在同层级进行, 不会跨层级比较
     在diff比较的过程中，循环从两边向中间比较

5.Q：什么是HTTP？HTTP与HTTPS的区别是什么？
  A：HTTP（HyperText Transfer Protocol）   hypertext n. 超文本（含有指向其它文本文件链接的文本） protocol n.礼仪，礼节；国际议定书，协议；
      HTTP即超文本传输协议，是实现网络通信的一种规范。HTTP是一种传输协议，即可以将数据由A间接直接到B，传输的数据是完整的数据如html文件，图片文件，查询结果等超文本，能够被上层应用识别。
      HTTPS：HTTP是明文传输，为了隐私、信息安全，将HTTP运行在SSL/TLS，通过SSL证书验证服务器身份并为浏览器和服务器之间通信进行加密，SSL协议位于TCP/IP协议与各种应用层协议之间
      区别：1：HTTPS是HTTP协议的安全版本，使用了SSL/TLS协议进行了加密处理，相对更安全。
            2：HTTPS与HTTP连接方式不同，默认端口不同，HTTP是80,HTTPS是443
            3.HTTPS需要加密和多次握手，性能不如HTTP
            4.HTTPS需要SSL，SSL证书需要钱
continue...
