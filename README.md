### 面试

公司 | 机试 | 一面 | 二面 | offer
-- | -- | -- | -- | --
华为OD | :heavy_check_mark: | :heavy_check_mark: | 放弃 | 
龙湖 | :heavy_check_mark: | :x: | 
百词斩 | — | :x: |
叫叫学院 | — | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:
同程艺龙 | — | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:
51talk | — | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:

### 目录

- [华为OD](#华为od)
- [龙湖](#龙湖)
- [百词斩](#百词斩)
- [叫叫学院](#叫叫学院)
- [同程艺龙](#同程艺龙)
- [51talk](#51talk)
- [总结](#总结)
- [参考](#参考)

#### 华为OD

hr主动通过boss联系我，打电话说是否有了解过华为外包，让我接收短信上平台做题

**机试**

机试总共3道题

1. 描述与[和为s的两个数字](https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof/)的描述一致，都是递增数组，差异在于求的是返回的数量<br>举个极端的例子，int数组 = \[1,2,2,2,4\]，数组中任意两数之和等于4的数量为3，有 (arr\[1],arr\[2]) (arr\[2],arr\[3]) (arr\[1],arr\[3])

2. 火星文计算器，有2种计算符号，`&`与`#`，`x&y=2x+3y`，`x#y=3x-2y`，`&`的计算优先级高于`#`，计算任意的火星文字符串(字符串只包含正整数与`&#`，且表达式合法)，输出答案<br>
比如`1#2&3#4`，先算`2&3=13`，转换成`1#13#4=-23#4=-77`<br>
leetcode上相关的题: [224. 基本计算器](https://leetcode-cn.com/problems/basic-calculator/) [227. 基本计算器 II
](https://leetcode-cn.com/problems/basic-calculator-ii/) [770. 基本计算器 IV](https://leetcode-cn.com/problems/basic-calculator-iv/)

3. 描述不清，略过

**机试结果**

没过多久hr打电话说机试过了，邀请视频一面

**视频一面**

晚上8点进行的视频面试，感觉很糟糕，看不到面试官的脸，盲面，第一次接触这种看不到脸的面试

先做了自我介绍，问了一些常规的问题，裸面，答得很差

最后整了一道远程ide编程题

```java
//  入参是left与right2个Iterator，返回left与right中按照元素从小到大排序的Iterator,实现此方法
Iterator<Integer> newIterable(Iterator<Integer> left, Iterator<Integer> right){
}
```

一个答案

```java
    Iterator<Integer> newIterable(Iterator<Integer> left, Iterator<Integer> right) {

        return new Iterator<Integer>() {

            Integer leftPoint;
            Integer rightPoint;

            @Override
            public boolean hasNext() {
                return left.hasNext() || right.hasNext() || leftPoint != null || rightPoint != null;
            }

            @Override
            public Integer next() {

                if (leftPoint == null && left.hasNext()) leftPoint = left.next();
                if (rightPoint == null && right.hasNext()) rightPoint = right.next();
                
                Integer temp;

                if(leftPoint == null) {
                    temp = rightPoint;
                    rightPoint = null;
                    return temp;
                }

                if(rightPoint == null){
                    temp = leftPoint;
                    leftPoint = null;
                    return temp;
                }

                if (leftPoint > rightPoint) {
                    temp = rightPoint;
                    rightPoint = null;
                    return temp;
                } else {
                    temp = leftPoint;
                    leftPoint = null;
                    return temp;
                }
            }
        };
```

**后续**

神奇的事情出现了，没过几天我先收到了面试没过的邮件，隔了一会儿又收到了面试通过的邮件

又隔了几天Hr打电话说面试通过了，邮件问题是内部人员搞错了，我以找到了工作回绝了二面

#### 龙湖

**机试**

bugfree平台，几道java选择题 + 一道算法 + 一道sql题 + 问答题(视频录制)

算法题与问答题已经忘了

sql题 [178. 分数排名](https://leetcode-cn.com/problems/rank-scores/)

**二面**

1. 说一下java里面对象的生命周期，从new 到销毁
2. 抽象类可以实例化吗？
3. 说一下快速排序的原理
4. 说一下java语言的特点，多态是什么意思？
5. 说一下java的GC，说下CMS和G1垃圾回收器
6. spring里面@Resource与@Autowired有什么区别？ 
7. 说下redis的数据类型与你常用的命令
8. 缓存雪崩应对方案？除了本地缓存还有其他方案没? 
9. mysql里面varchar与char有什么区别?
10. mysql有哪几种存储引擎说一说?
11. mysql的myisam与innodb在crud上效率的区别
12. 说下java里面sync

**后续**

第二天通知没过

#### 百词斩

**一面**

1. 项目用的什么技术，你具体负责什么?
2. mybatis怎么级联查询?知道N+1查询查询吗？
3. 简述下OSI 5层或者7层模型,路由在哪一层？HTTP在哪一层，TCP/IP在哪一层?
4. spring 里面@bean是用来干啥的？分别作用在final、static、private 方法上有效果吗？
5. spring boot 里面@Configuration注解的proxyBeanMethods字段作用是?
6. 操作系统对于线程同步有哪些方法？

算法题:
[最长不含重复字符的子字符串](https://leetcode-cn.com/problems/zui-chang-bu-han-zhong-fu-zi-fu-de-zi-zi-fu-chuan-lcof/)<br>
智力题:[翻牌](https://zhidao.baidu.com/question/164460624.html)

**后续**

第二天收到邮件挂

#### 叫叫学院

**一面&二面**

1. 消息队列怎么保证消息被消费？
2. 订单关键流程API上幂等如何实现？
3. redis与zk的分布式锁有什么区别？
4. 数据库与缓存的双写问题如何解决？分布式事务的TCC是怎么一回事,还有其他解决方案吗？
5. 电商中下订单立即扣库存与订单支付后扣库存有何区别？
6. `notify`与`notifyAll`的底层实现?

**后续**

发offer后要在1天之内立即确认，拒了

#### 同程艺龙

**一面**

1. 先来就考察2道dp,[斐波那契数列](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/),[动态规划之二项式系数](https://www.cnblogs.com/passion-sky/p/9193163.html)
2. java手写单例模式
3. 说下`voliate`的作用
4. 说下java线程池参数意思与内部实现

**二面**

1. 项目的qps/tps是多少？负责的服务部署了几个节点？
2. 一般怎么进行jvm调优，参数的设置?用的什么垃圾收集器?
3. 线上遇到异常如何解决？如何排查？ 
4. 如果进行压测，压测打满了，但是cpu占用率缺不高，如何排查？
5. 说下netty的内部模型，有那么多NIO的线程模型，为什么用netty?
6. redis为什么那么快？

**hr面**

基本没问啥，为什么换工作，出于什么考量等


#### 51talk

**一面**

1. 如何处理双写一致性?
2. 生产有没有遇到过OOM，怎么排查解决的？
3. BIO/NIO/AIO分别是什么意思？

**二面**

不太舒服，面试官态度很随意，我就面的很随意

1. 问了下项目的流程，项目使用的技术栈，以及QPS
2. 手撕算法题[最小硬币数](https://blog.csdn.net/weixin_39831546/article/details/81506559)
3. 手撕快速排序(说了个大概，不想写了)
4. 问有没有什么职业规划，中长远期目标，如何落地实现(都是扯淡性质，**我说我边上班边考研可以么？**，瞎扯淡即可)

最后我问了下成都负责什么具体业务，面试官说你1面问过没有，我说问过，他说"问过就别问了，问要问你没问的。"

当场失语，没任何想问的了，结束

**hr面**

问你手上还有什么其他offer

#### 总结

先把自己的项目说清楚(业务流程、担任角色、技术架构)，这点很重要，项目说不清楚印象比较差

项目的QPS/TPS/PV什么乱七八糟的参数都要记住，编都行。线上服务的节点、CPU、内存，编。监控告警、JVM调优、线上排查、故障恢复等，先自己复盘下，假的都行，说的时候有底气，像真的即可

我遇见的面试官的3种逻辑:

1. 基于你的项目经历往细节或者难点问，比如我之前负责过医药电商多人团业务，就会问并发情况下怎么保障不超卖、下单扣库存和支付扣库存的区别、分布式锁业务上的具体使用场景等
2. 基于简历上的技术点上开问，比如你写了`熟练运用dubbo...`，可能就会问到，dubbo的结构，dubbo是什么东西，用来解决什么问题,生产者的大概启动流程？(技术知识)、dubbo的使用方法，如果要设置超时时间怎么配置,默认配置是多少？(考察你实际有没有用过)
3. 不基于你的简历，自己有一套技术问题问，这种多发生于集中面试，面试官自己有一套问题，看应聘者谁答的比较好，择优录取

**高频技术问题**

这类问题面试问的比较多，整理了一下:

1. 数据库与缓存的双写问题
2. 分布式锁实现
3. 消息队列怎么保障不重复消费(幂等)，怎么保障消息不丢失，常用的消息队列内部实现
4. 项目的qps,tps,JVM,java多线程,垃圾收集器,线上JVM参数设置的多少,生产出事故，如何解决？


**灵魂拷问**

面试中遇到的灵魂拷问，经常引起大脑一片空白，需要现编的那种，很想锤面试官，**你问NM呢?问就是立即辞职，准备考研**

此类问题hr与技术面都喜欢问

2. 职业生涯规划？中短期规划？之前有没有什么计划如何落地的？
3. 在项目中负责什么角色？做了什么事？
4. 你觉得你的性格怎么样？优势是什么？劣势是什么？
5. 最有成就感的事是什么？做的最糟糕的事是什么？
6. 工作中如果遇到跟测试或者前端理解不一致的时候，如何解决？
7. 平时怎么提升自我水平？喜欢看什么书？从哪些渠道提升技术实力？
8. 都看过哪些源码，有没有分享的?最后有什么提升？

#### 参考

肝算法:
https://github.com/labuladong/fucking-algorithm<br>leetcode中文网站


简历常用例句: 
https://github.com/resumejob/awesome-resume

后端提高:
(这个看的比较多，都是高频的知识点)https://github.com/doocs/advanced-java
https://github.com/rbmonster/learning-note<br>
https://github.com/donnemartin/system-design-primer/blob/master/README-zh-Hans.md

书籍:
深入理解java虚拟机(第三版) - 内存模型，垃圾回收<br>
Redis 深度历险：核心原理与应用实践 - 持久化，数据结构，主从/哨兵/集群模式, 分布式锁<br>
网络相关的书也看下




