# AndroidOffer

## Java 

### Java 进阶

### 容器

HashMap、HashSet、LinkedList、ArrayList、数组等）,需要了解其实现原理，还要灵活运用，如：自己实现 LinkedList、两个栈实现一个队列，数组实现栈，队列实现栈等。

HashMap、HashTable 和 CurrentHashMap 的核心区别（并发），其次内部数据结构的实现、扩容、存取操作，再深一点 哈希碰撞，哈希计算，哈希映射，为什么是头插法，扩容为什么是 2 的幂次等。

1. [到底什么是 Hash 算法]( https://www.cnblogs.com/lanqi/p/10634734.html )

2. [HashMap原理深入理解](https://blog.csdn.net/visant/article/details/80045154) 

3. [从源码角度认识ArrayList，LinkedList与HashMap](https://www.jianshu.com/p/f174d49b391c)

4. [解决哈希冲突的常用方法分析](https://www.jianshu.com/p/4d3cb99d7580)

5. 对比：Hashtable、HashMap、LinkedHashMap、ConcurrentHashMap、TreeMap （看第六条就可以）

6. [我对 HashMap 的概括](https://github.com/hgncxzy/AndroidOffer/blob/master/docs/HashMap.md)

   

### JVM  &  内存模型  & 内存回收 & 状态机

1. [JVM虚拟机内存结构，以及它们的作用](https://github.com/hgncxzy/offer/blob/master/docs/jvm%20虚拟机.md)
2. [理解Java内存模型](https://juejin.im/post/5bf2977751882505d840321d)
3. [你了解Java内存模型么（Java7、8、9内存模型的区别）](https://blog.csdn.net/laomo_bible/article/details/83067810)
4. [Java虚拟机（JVM）你只要看这一篇就够了！](https://blog.csdn.net/qq_41701956/article/details/81664921)
5. JVM 类加载机制
6. 垃圾回收算法对比
7. JVM 内存区域，开线程影响哪块区域内存？
8. [对 Dalvik、ART 虚拟机有什么了解？对比？](https://github.com/hgncxzy/AndroidOffer/blob/master/docs/Dalvik、ART 虚拟机对比.md)
9. 垃圾回收机制和调用 System.gc()的区别？
10. 谈谈对 java 状态机的理解。 

### 反射



### 多线程和线程池

1. 线程有哪些状态，哪些锁，各种锁的区别
2. 并发编程：synchronized 和 volatile 、ReentrantLock 、CAS 的区别
3. synchronized 修饰实例方法和修饰静态方法有啥不一样。
4. 线程阻塞的方式，sleep 、wait、yield、join 的区别，wait 的线程如何唤醒它
5. java中创建线程的方式有几种。 一般而言很多人会回答两种，Thread与Runnable。我最早面试的时候也是说这两种，然后面试官问还有别的吗？我当时就没答上来，其实还有一种叫Callable的。
6. 这里可能还需要理解下Callable与Runnable的区别以及使用时候的注意事项。
7. 死锁造成的原因、手写死锁。synchronized 关键字
8. 线程池 ThreadPoolExecutor 的使用，内部处理任务的过程以及四种线程池的区别。

### HTTP、HTTPS、TCP/IP、Socket 通信、三次握手四次挥手过程

计算机网络部分： 

1. TCP 有哪些状态 
2. 三次握手、四次挥手。为啥不是三次不是两次
3. HTTPS 和 HTTP 的区别，HTTPS 2.0 3.0？
4. 浏览器输入一个 URL 按下回车网络传输的流程？ 
5. 问的深一点的可能涉及到网络架构，每层有什么协议，FTP 相关原理，例：TCP 建立连接后，发包频率是怎么样的？
6. [HTTP 状态码](https://blog.csdn.net/Eric_sun8868/article/details/102862171)

### 设计模式

六大基本原则、项目中常用的设计模式、手写单例等.([参考](https://java-design-patterns.com/patterns/))

1. 设计模式六大基本原则
2. [单例模式(饿汉(饥汉)、懒汉(饱汉)、懒汉优化)](https://www.jianshu.com/p/18d70ba44ca5) 
3. [单例模式三种模式，饿汉、饱汉、双重锁模式，实例及优劣详解](https://blog.csdn.net/zhangliangzi/article/details/52438401)
4. [Java的生产者-消费者模型 ](https://blog.csdn.net/wowwilliam0/article/details/80875673)
5. 双亲委托模型为什么如此设计
6. 生产者模式和消费者模式的区别？ 
7. 单例模式双重加锁，为什么这样做？ 
8. 项目中常用的设计模式有哪些？
9. 手写观察者模式代码。
10. 适配器模式、装饰者模式、外观模式的异同？
11. 谈谈应用更新（灰度、强制更新、分区更新？） -- 写一篇文章 

### Java 四大引用

1. Java中的四种引用以及使用的场景

### 泛型

Java 的泛型，<? super T> 和 <? extends T> 的区别。问到泛型、泛型擦除、通配符相关的东西

### final、finally、finalize 的区别
### 接口、抽象类的区别

### 算法

1. 合并排序
2. 快速排序
3. 堆排序
4. 傅利叶变换与快速傅利叶变换
5. 迪杰斯特拉算法（又译戴克斯特拉算法）
6. RSA 算法
7. 安全哈希算法
8. 整数分解
9. 链接分析
10. 比例微积分算法
11. 数据压缩算法
12. 随机数生成算法

## Android

### 四大组件之 Activity

四大组件内容 参考 这个  https://www.jianshu.com/p/0f52a3defc1d 

1. [startActivity 的内部实现](https://www.jianshu.com/p/ece2790efc9f)
2. [Activity 与 Window 与 View 之间的关系]( https://blog.csdn.net/freekiteyu/article/details/79408969?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1.nonecase&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1.nonecase )
3. 四种启动模式 standard、singleTop、singleTask、singleInstance 的区别。
4. onNewIntent 的调用时机
5. 不同栈之间的 Activity 如何跳转。
6. Activity 生命周期

### 四大组件之 Service

1. Service 的启动模式
2. Service 的生命周期
3. Binder 和 IntentService
4. IntentService 的原理和源码

### 四大组件之 BroadcastReceiver

1. 

### 四大组件之 ContentProvider

1. 

### Android 消息机制

参考  https://blog.csdn.net/haoxuhong/article/details/80103030 和 Android.doc

1. 线程间通讯 ——— Handler，HandlerThread等。 

2. 组件间通信 ——— BroadcastReceiver，接口回调等。 

3. 第三方通信 ——— EventBus，rxBus 

4. 进程间通信 ——— Content Provider ，Broadcast ，AIDL等。 

5. 长连接推送 ——— WebSocket，XMPP等。

6. 异步消息处理机制 ———  Handler 与 AsyncTask 的区别

7. 异步消息处理机制 ———  HandlerTask

8. 异步消息处理机制 ———  IntentService

9. 异步消息处理机制 ———  AsyncTask内部实现原理

10. 异步消息处理机制 ———  内部处理多任务是串行还是并行处理，为什么是串行处理，如果让其变成并行处理等

    

### AMS、WMS、PMS

1. 

### 缓存

1. LruCache算法如何实现，内部为什么要用LinkHashMap来实现。

### 图片处理

1. 图片的压缩处理。
2.  这里会问四种图片格式的区别(ARGB888、RGB565、RGB444、Alpha_8)
3. 给出一张以上格式的图片如何计算图片所占的内存大小。

### 序列化

1. Serializable与Parcable的区别。 
2. 在什么情况下需要用到序列化和反序列化，
3. Serializable中为什么要设置UID，设置UID与不设置UID值的区别和影响。

### 动画

1. 动画总结。
2.  重点是属性动画内部实现原理，差值器和估值器的使用。

### 断点续传

1. Android中断点续传的原理

### 热更新  & 组件化 & 插件化

1. 热更新的原理 
2. 组件化原理
3. 插件化原理

### 性能优化

1. [Android 性能优化 01 - UI 优化]( https://blog.csdn.net/freekiteyu/article/details/77862670 )
2. [Android 性能优化 02 - 内存优化]( https://blog.csdn.net/freekiteyu/article/details/78060938 )
3. [Android 性能优化 03 - 网络优化]( https://www.jianshu.com/p/8301af3a2902 )
4. [Android 如何保持 App 的稳定性 ](https://www.jianshu.com/p/400a268e8671)
5. [Android的性能优化。](https://blog.csdn.net/jdfkldjlkjdl/article/details/89495181)
6. Android 内存泄漏的检测方式
7. Android OOM & ML & ANR 造成的原因
8. 冷启动和热启动以及冷启动原理以及优化

### 网络请求的原理

1. 网络请求原理。
2.  http与https的区别、
3. 三次握手和四次挥手，为什么握手一定要三次？为什么挥手一定要四次？
4. http的响应码。
5. http1与http2的区别等。

### 开源框架

1. 开源框架的使用和原理。
2.  OkHttp 内部实现、
3. glide 的内部原理、
4. EventBus 源码
5. RxJava 的使用过程注意事项等。
   

### Android View

1. [Android View 的绘制流程](https://www.jianshu.com/p/c151efe22d0d)
2. [Android View 的绘制流程](https://blog.csdn.net/pgg_cold/article/details/79481301)
3. [Android的wrap_content是如何计算的](https://www.jianshu.com/p/2af18625fcdd)

### 事件传递

1. [请简述Android事件传递机制](https://github.com/hgncxzy/offer/blob/master/docs/Android事件传递机制.md)
2. [ACTION_CANCEL事件何时触发？](https://github.com/hgncxzy/offer/blob/master/docs/ACTION_CANCEL事件何时触发？.md)
3. onInterceptTouchEvent返回true时剩下的MOVE与UP如何走
4. onTouch、onTouchEvent、onClick的先后顺序关系。

### 进程  & 线程  & 线程池

1. [Android 的进程间通信](https://blog.csdn.net/hzw2017/article/details/81275438)
2. [Liunx 操作系统的进程间通信](https://www.cnblogs.com/jxc321/p/9296571.html)
3. [Android 进程与线程的区别与联系](https://www.jianshu.com/p/f3feb05e3281)
4. ThreadPoolExcutor 原理
5. IPC原理
6. AIDL
7. Binder
8. 进程之间的优先级。 前台进程、可见进程、后台进程、不可见进程与空进程。
9. 进程的保活措施。

### 音视频开发

1. IPB 帧的解码和渲染顺序
2. 对 h264 aac opus 这几个协议是否有了解
3. udp传输音视频桢 如何解决丢包问题
4. 

## Android 三方框架

### RxJava

1. [RxJava 1与RxJava 2的API上的区别]( https://www.jianshu.com/p/d53463e1c3d6)
2. [RxJava常见的使用场景总结](https://www.jianshu.com/p/6917510b0e4c)
3. [可能是东半球最全的RxJava使用场景小结](https://blog.csdn.net/theone10211024/article/details/50435325)
4. [我写的例子 RxJava2Demo](https://github.com/hgncxzy/RxJava2Demo)

## 非技术方面

1. [怎样写简历](https://github.com/hgncxzy/AndroidOffer/blob/master/docs/非技术面试/1.md)
2. [当面试官问“你有什么要问我的吗”时，应该说什么？](https://github.com/hgncxzy/AndroidOffer/blob/master/docs/非技术面试/2.md)

## 其他面试链接

1. [2019年最新总结，阿里，腾讯，百度，美团，头条等技术面试题目，以及答案，专家出题人分析汇总。](https://github.com/0voice/interview_internal_reference)
2. [Java 工程师成神之路](https://github.com/hollischuang/toBeTopJavaer)
3. https://github.com/kdn251/interviews/blob/master/README-zh-cn.md
4. 