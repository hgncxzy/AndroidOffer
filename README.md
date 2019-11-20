# offer
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

    

### 设计模式

1. [单例模式(饿汉(饥汉)、懒汉(饱汉)、懒汉优化)](https://www.jianshu.com/p/18d70ba44ca5) 
2. [单例模式三种模式，饿汉、饱汉、双重锁模式，实例及优劣详解](https://blog.csdn.net/zhangliangzi/article/details/52438401)
3. [Java的生产者-消费者模型 ](https://blog.csdn.net/wowwilliam0/article/details/80875673)
4. 

### 集合  & 数据结构

1. [HashMap的内部结构？ 内部原理? ](https://blog.csdn.net/dixialaoshu4/article/details/84331169)
2. [HashMap原理深入理解](https://blog.csdn.net/visant/article/details/80045154)
3. 

### 问题

1. [请简述Android事件传递机制](https://www.cnblogs.com/fuly550871915/p/4983682.html)， ACTION_CANCEL事件何时触发？

   （1）正常情况下，android中的事件是必须要经过传递流程然后再经过处理流程的。要记住这个先后的顺序。

   （2）在传递流程和处理流程中，你都可以修改方法的返回值，来对流程做控制。如下：
             对于事件的拦截，我们主要重写就是OnInterceptTouchEvent和onTouchEvent方法。两句就可以总结：

       事件的传递，返回结果为true，表示拦截，不再往下传递，为false，不拦截，继续往下传递。主要针对的就是OnInterceptTouchEvent方法。
       事件的处理，返回结果为true，表示拦截，不再往上传递（即我处理的很完美，不需要你再来审核我！），返回结果为false（没有成功处理事件），继续向上传递。针对就是onTouchEvent方法。

   （3）如果流程你还理解，就好好想一想那个公司员工的拟人化解释吧！实际上android的事件处理机制原理就是这样子的！

   **ACTION_CANCEL事件何时触发？**

   关于 ACTION_CANCEL 何时被触发，系统文档有这么一种使用场景：在设计设置页面的滑动开关时，如果不监听ACTION_CANCEL，在滑动到中间时，如果你手指上下移动，就是移动到开关控件之外，则此时会触发ACTION_CANCEL，而不是 ACTION_UP，造成开关的按钮停顿在中间位置。 
   意思是当滑动的时候就会触发，不知道大家搞没搞过微信的长按录音，有一种状态是“松开手指，取消发送”，这时候就会触发 ACTION_CANCEL。

2. 

### 进程  & 线程

1. Android 的进程间通信，Liunx 操作系统的进程间通信。
2. 

