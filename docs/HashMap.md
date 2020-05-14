## ### hashing (哈希法) 的概念

散列法（Hashing）是一种将字符组成的字符串转换为固定长度（一般是更短长度）的数值或索引值的方法，称为散列法，也叫哈希法。由于通过更短的哈希值比用原始值进行数据库搜索更快，这种方法一般用来在数据库中建立索引并进行搜索，同时还用在各种解密算法中。

## ### 对比：Hashtable、HashMap、LinkedHashMap、ConcurrentHashMap、TreeMap

#### HashTable

Hashtable 是早期Java类库提供的一个哈希表实现。

本身是同步的。

 HashTable 和 HashMap 的实现原理几乎一样，差别无非是：

不支持 null 的键和值，由于同步导致的性能开销，所以已经很少被推荐使用。

HashTable 是线程安全的。但是 HashTable 线程安全的策略实现代价却太大了，简单粗暴，get/put 所有相关操作都是synchronized 的，这相当于给整个哈希表加了一把大锁。多线程访问时候，只要有一个线程访问或操作该对象，那其他线程只能阻塞，相当于将所有的操作串行化，在竞争激烈的并发场景中性能就会非常差。 

#### HashMap

HashMap 是无序的，线程不安全的。

HashMap与 HashTable主要区别在于 HashMap 不是同步的，支持 null 的键和值等。

通常情况下，HashMap 进行 put 或者 get 操作，可以达到常数时间的性能，所以它是绝大部分利用键值对存取场景的首选。

 由于 HashMap 是线程不安全的，在多线程环境下，使用 Hashmap 进行 put 操作会引起死循环，导致 CPU 利用率接近100%，所以在并发情况下不能使用 HashMap。

 #### LinkedHashMap

因为 HashMap 是无序的，当我们希望有顺序地去存储 key-value 时，就需要使用 LinkedHashMap 了。

LinkedHashMap 默认的构造参数是默认插入顺序的，就是说你插入（put）的是什么顺序，读（get）出来的就是什么顺序.

但是也有访问顺序，就是说你访问了一个 key，这个 key 就跑到了最后面.这里 accessOrder 设置为false，表示不是访问顺序而是插入顺序存储的，这也是默认值，表示 LinkedHashMap 中存储的顺序是按照调用 put 方法插入的顺序进行排序的。 

#### ConcurrentHashMap

主要就是为了应对 HashMap 在并发环境下不安全而诞生的，ConcurrentHashMap 的设计与实现非常精巧，大量的利用了volatile，final，CAS 等 lock-free 技术来减少锁竞争对于性能的影响。

我们都知道 Map 一般都是数组+链表结构.

ConcurrentHashMap 避免对全局加锁，只对局部加锁操作，这样就极大地提高了并发环境下的操作速度，由于ConcurrentHashMap 在 JDK1.7 和 1.8 中的实现非常不同，接下来我们谈谈 JDK 在 1.7 和 1.8 中的区别。

##### ConcurrentHashMap 在 JDK 1.7 和 JDK 1.8 中实现的区别

 在 JDK1.7 中 ConcurrentHashMap 采用了数组+Segment+分段锁的方式实现。

JDK8 中 ConcurrentHashMap 参考了 JDK8 HashMap 的实现，采用了数组+链表+红黑树的实现方式来设计，内部大量采用 CAS 操作，这里我简要介绍下 CAS（比较交换）。

CAS 是 compare and swap 的缩写，即我们所说的比较交换。cas 是一种基于锁的操作，而且是乐观锁。

在 java 中锁分为乐观锁和悲观锁。

悲观锁是将资源锁住，等一个之前获得锁的线程释放锁之后，下一个线程才可以访问。

而乐观锁采取了一种宽泛的态度，通过某种方式不加锁来处理资源，比如通过给记录加 version 来获取数据，性能较悲观锁有很大的提高。

#### TreeMap

TreeMap 则是基于红黑树的一种提供顺序访问的 Map，和 HashMap 不同，它的 get、put、remove 之类操作时间复杂度都是 O（log(n)），具体顺序可以由指定的 Comparator 来决定，或者根据键的自然顺序来判断。主要用于排序，默认排序为升序。如果要改变其排序可以自己写一个Comparator。

### HashMap 概念和底层结构

HashMap 是基于哈希表的Map接口的非同步实现。

此实现提供所有可选的映射操作，并允许使用 null 值和 null 键。

HashMap 储存的是键值对，HashMap很快。

此类不保证映射的顺序，特别是它不保证该顺序恒久不变。

#### HashMap 内部结构

可以看作是数组和链表结合组成的复合结构。

其中，数组被分为一个个桶（bucket），每个桶存储有一个或多个 Entry 对象，每个 Entry 对象包含三部分 key（键）、value（值），next (指向下一个 Entry）。

通过哈希值决定了 Entry 对象在这个数组的寻址；哈希值相同的 Entry 对象（键值对），则以链表形式存储。

如果链表大小超过树形转换的阈值（TREEIFY_THRESHOLD= 8），链表就会被改造为树形结构。

### 如何重新调整 HashMap 的大小

“如果 HashMap 的大小超过了负载因子(load factor)定义的容量，怎么办？”

HashMap 的扩容阈值（threshold = capacity* loadFactor 容量范围是16~2的30次方），就是通过它和 size 进行比较来判断是否需要扩容。默认的负载因子大小为 0.75，也就是说，当一个 map 填满了 75% 的 bucket 时候，和其它集合类(如ArrayList 等)一样，将会创建原来 HashMap 大小的两倍的 bucket 数组（jdk1.6，但不超过最大容量），来重新调整 map的大小，并将原来的对象放入新的 bucket 数组中。这个过程叫作 rehashing，因为它调用 hash 方法找到新的 bucket 位置。

### HashMap 扩容为何是  2  的倍数

从 hashMap 源码中获取元素的位置的函数来讲解，

```java
static int indexFor(int h, int length) {
// assert Integer.bitCount(length) == 1 : "length must be a non-zero power of 2";
return h & (length-1);
}
```

解释：

h:为插入元素的 hashcode

 length:为 map 的容量大小

&：与操作 比如 1101 & 1011=1001

 如果 length 为 2 的次幂 则 length-1 转化为二进制必定是11111……的形式，再和 h 的二进制进行与操作效率会非常的快，而且空间不浪费；

如果 length 不是 2 的次幂，比如 length 为 15 ，则 length-1 为 14，对应的二进制为 1110，再与 h 与操作，最后一位都为0，而 0001，0011，0101，1001，1011，0111，1101 这几个位置永远都不能存放元素了，空间浪费相当大。

更糟的是这种情况中，数组可以使用的位置比数组长度小了很多，这意味着进一步增加了碰撞的几率，减慢了查询的效率！这样就会造成空间的浪费。

所以当扩容为 2 的倍数时，可以：

1. 降低了碰撞的几率

2. 提高了查询的效率

3. 避免空间的浪费

    

### hashmap 中默认的数组大小是多少

查看源代码可以得知是16，

为什么是 16，而不是 15，也不是 20 呢，显然是因为 16 是 2 的整数次幂的原因，在小数据量的情况下 16 比 15 和 20 更能减少 key 之间的碰撞，而加快查询的效率。 

所以，在存储大容量数据的时候，最好预先指定 hashmap 的 size 为 2 的整数次幂次方。就算不指定的话，也会以大于且最接近指定值大小的 2 次幂来初始化的。

### 解决 hash 冲突的常见方法

针对哈希表直接定址可能存在hash冲突，举一个简单的例子，例如：

第一个键值对A进来，通过计算其key的hash得到的index=0。记做:Entry[0] = A。

第二个键值对B，通过计算其index也等于0， HashMap会将B.next =A,Entry[0] =B,

第三个键值对C，通过计算其index也等于0，那么C.next = B,Entry[0] = C；

这样我们发现index=0的地方事实上存取了A,B,C三个键值对,它们通过next这个属性链接在一起。 对于不同的元素，可能计算出了相同的函数值，这样就产生了hash 冲突，那要解决冲突，又有哪些方法呢？具体如下：

a. 链地址法：将哈希表的每个单元作为链表的头结点，所有哈希地址为 i 的元素构成一个同义词链表。即发生冲突时就把该关键字链在以该单元为头结点的链表的尾部。

b. 开放定址法：即发生冲突时，去寻找下一个空的哈希地址。只要哈希表足够大，总能找到空的哈希地址。

c. 再哈希法：即发生冲突时，由其他的函数再计算一次哈希值。

d. 建立公共溢出区：将哈希表分为基本表和溢出表，发生冲突时，将冲突的元素放入溢出表。

### HashMap 采用哪种方法解决冲突的呢？

HashMap 就是使用链地址法来解决冲突的（jdk8 中采用平衡树来替代链表存储冲突的元素，但 hash() 方法原理相同）。当两个对象的 hashcode 相同时，它们的 bucket 位置相同，碰撞就会发生。此时，可以将 put 进来的 K- V 对象插入到链表的尾部。对于储存在同一个 bucket 位置的链表对象，可通过键对象的 equals()  方法用来找到键值对。