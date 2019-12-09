# AndroidOffer

## Java 

### 集合  & 数据结构 & 容器

**容器**（HashMap、HashSet、LinkedList、ArrayList、数组等）,需要了解其实现原理，还要灵活运用，如：自己实现 LinkedList、两个栈实现一个队列，数组实现栈，队列实现栈等。

HashMap、HashTable 和 CurrentHashMap 的核心区别（并发），其次内部数据结构的实现、扩容、存取操作，再深一点 哈希碰撞，哈希计算，哈希映射，为什么是头插法，扩容为什么是 2 的幂次等。

1. [HashMap的内部结构？ 内部原理? ](https://blog.csdn.net/dixialaoshu4/article/details/84331169)
2. [HashMap原理深入理解](https://blog.csdn.net/visant/article/details/80045154)
3. [JAVA容器-自问自答学HashMap](https://www.jianshu.com/p/32f67f9e71b5)
4. [什么是HashMap？](https://juejin.im/post/5a215783f265da431d3c7bba)
5. [从源码角度认识ArrayList，LinkedList与HashMap](https://www.jianshu.com/p/f174d49b391c)
6. 

### JVM  &  内存模型  & 内存回收

1. [JVM虚拟机内存结构，以及它们的作用](https://github.com/hgncxzy/offer/blob/master/docs/jvm%20虚拟机.md)

2. [理解Java内存模型](https://juejin.im/post/5bf2977751882505d840321d)

3. [你了解Java内存模型么（Java7、8、9内存模型的区别）](https://blog.csdn.net/laomo_bible/article/details/83067810)

4. [Java虚拟机（JVM）你只要看这一篇就够了！](https://blog.csdn.net/qq_41701956/article/details/81664921)

5. JVM 类加载机制

6. 垃圾回收算法对比

7. JVM 内存区域，开线程影响哪块区域内存？

8. 对 Dalvik、ART 虚拟机有什么了解？对比？

   ART 的机制与 Dalvik 不同。在Dalvik下，应用每次运行的时候，字节码都需要通过即时编译器（just in time ，JIT）转换为机器码，这会拖慢应用的运行效率，而在ART 环境中，应用在第一次安装的时候，字节码就会预先编译成机器码，极大的提高了程序的运行效率，同时减少了手机的耗电量，使其成为真正的本地应用。这个过程叫做预编译（AOT,Ahead-Of-Time）。这样的话，应用的启动(首次)和执行都会变得更加快速。

   **优点：**

   - 系统性能的显著提升。
   - 应用启动更快、运行更快、体验更流畅、触感反馈更及时。
   - 更长的电池续航能力。
   - 支持更低的硬件。

   **缺点：**

   - 机器码占用的存储空间更大，字节码变为机器码之后，可能会增加10%-20%（不过在应用包中，可执行的代码常常只是一部分。比如最新的 Google+ APK 是 28.3 MB，但是代码只有 6.9 MB。）
   - 应用的安装时间会变长。

8. 垃圾回收机制和调用 System.gc()的区别？

### 类加载

1. **类加载过程**（需要多看看，重在理解，对于热修复和插件化比较重要）

### 反射

### 多线程和线程池

线程有哪些状态，哪些锁，各种锁的区别

并发编程：
synchronized 和 volatile 、ReentrantLock 、CAS 的区别

synchronized 修饰实例方法和修饰静态方法有啥不一样。

sleep 、wait、yield 的区别，wait 的线程如何唤醒它

### HTTP、HTTPS、TCP/IP、Socket 通信、三次握手四次挥手过程

计算机网络部分： 

1. TCP 有哪些状态 
2. 三次握手、四次挥手。为啥不是三次不是两次

3. HTTPS 和 HTTP 的区别，HTTPS 2.0 3.0？

4. 浏览器输入一个 URL 按下回车网络传输的流程？ 

5. 问的深一点的可能涉及到网络架构，每层有什么协议，FTP 相关原理，例：TCP 建立连接后，发包频率是怎么样的？

### 设计模式

六大基本原则、项目中常用的设计模式、手写单例等.



1. [单例模式(饿汉(饥汉)、懒汉(饱汉)、懒汉优化)](https://www.jianshu.com/p/18d70ba44ca5) 
2. [单例模式三种模式，饿汉、饱汉、双重锁模式，实例及优劣详解](https://blog.csdn.net/zhangliangzi/article/details/52438401)
3. [Java的生产者-消费者模型 ](https://blog.csdn.net/wowwilliam0/article/details/80875673)
4. 生产者模式和消费者模式的区别？ 
5. 单例模式双重加锁，为什么这样做？ 
6. 知道的设计模式有哪些？ 
7. 项目中常用的设计模式有哪些？
8.  手写生产者、消费者模式。 
9. 手写观察者模式代码。
10.  适配器模式、装饰者模式、外观模式的异同？
11.  谈谈对 java 状态机的理解。 
12. 谈谈应用更新（灰度、强制更新、分区更新？）

### 断点续传

### Java 四大引用

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



## Android View

1. [Android View 的绘制流程](https://www.jianshu.com/p/c151efe22d0d)
2. [Android View 的绘制流程](https://blog.csdn.net/pgg_cold/article/details/79481301)
3. [Android的wrap_content是如何计算的](https://www.jianshu.com/p/2af18625fcdd)

### 事件传递

1. [请简述Android事件传递机制](https://github.com/hgncxzy/offer/blob/master/docs/Android事件传递机制.md)

2. [ACTION_CANCEL事件何时触发？](https://github.com/hgncxzy/offer/blob/master/docs/ACTION_CANCEL事件何时触发？.md)

### 进程  & 线程

1. [Android 的进程间通信](https://blog.csdn.net/hzw2017/article/details/81275438)
2. [Liunx 操作系统的进程间通信](https://www.cnblogs.com/jxc321/p/9296571.html)
3. [Android 进程与线程的区别与联系](https://www.jianshu.com/p/f3feb05e3281)
4. 



### 其他面试链接

1. [2019年最新总结，阿里，腾讯，百度，美团，头条等技术面试题目，以及答案，专家出题人分析汇总。](https://github.com/0voice/interview_internal_reference)

2. 