# 一.概述

## 1.是什么

Redis：$\textcolor{red}{RE}$mote $\textcolor{red}{D}$ictionary $\textcolor{red}{S}$erver(远程字典服务器)

官网解释：

Remote Dictionary Server$\textcolor{red}{远程字典服务器}$是完全开源的，使用ANSIC语言编写遵守BSD协议，是一个高性能的Key-Value数据库，提供了丰富的数据结构，例如String、Hash、List、Set、SortedSet等等。数据是存在内存中的，同时Redis支持事务、持久化、LUA脚本、发布/订阅、缓存淘汰、流技术等多种功能，提供了主从模式、Redis Sentinel和Redis Cluster集群架构方案

![Redis介绍](D:\java学习课件\Redis7\1.Redis入门概述\images\1.Redis介绍.jpg)

$\textcolor{red}{安特雷兹}$

个人github：github.com/antirez

个人博客：antirez.com/latest/0

## 2.能干嘛

### 主流功能与应用

$\textcolor{red}{1.分布式缓存，挡在MySQL数据库之前的带刀护卫}$

![](D:\java学习课件\Redis7\1.Redis入门概述\images\2.Redis获取数据简图.jpg)

### 与传统数据库关系(MySQL)

​	·Redis是key-value数据库(**NoSQL**一种)，MySQL是关系型数据库

​	·Redis数据操作主要在内存，而MySQL主要存储在磁盘

​	·Redis在某一些场景使用中要明显优于MySQL，比如计数器、排行榜等方面

​	·Redis通常用于一些特定场景，需要与MySQL一起配合使用

​	·$\textcolor{red}{两者并不是相互替换和竞争的关系，而是共用和配合使用}$

2.内存存储和持久化（RDB和AOF）

​	Redis支持异步将内存中的数据写到硬盘上，同时不影响继续服务

3.高可用架构搭配

​	单机、主从、哨兵、集群

4.缓存穿透、击穿、雪崩

5.分布式锁

6.队列

​	Redis提供list和Set操作，这使得Redis能作为一个很好的消息队列平台来使用。

​	我们常通过Redis的队列功能做购买限制。比如到了节假日或者推广期间，进行一些活动，对用户购买行为进行限制，限制今天只能购买几次商品或者一段时间内只能购买一次。也比较适合使用。

7.排行榜+点赞

​	在互联网应用中，有各种各样的排行榜，如电商网站的月度销量排行榜、社交APP的礼物排行榜、小程序的投票排行榜等等。Redis提供的zset数据类型能够快速实现这些复杂的排行榜。

​	比如小说网站对小说进行排名，根据排名，将排名靠前的小说推荐给用户。

## 总体功能概述

![](D:\java学习课件\Redis7\1.Redis入门概述\images\3.总体功能概述.jpg)

##### 优势：

​	性能极高-Redis读的速度是110000次/秒，写的速度是81000次/秒

​	Redis数据类型丰富，不仅仅支持简单的Key-Value类型的数据，同时还提供list，set，zset，hash等数据结构的存储

​	Redis支持数据的持久化，可以将内存中的数据保持在磁盘中，重启的时候可以再次加载进行使用

​	Redis支持数据的备份，即master-slave模式的数据备份

### 小总结

![](D:\java学习课件\Redis7\1.Redis入门概述\images\4.小总结.jpg)

## 3.去哪下

官网地址: 

英文：https://redis.io/

中文：http://www.redis.cn/	https://www.redis.com.cn/documentation.html

安装包：https://redis.io/download/，选择redis7.0版本即可

![](D:\java学习课件\Redis7\1.Redis入门概述\images\5.Redis英文官网.jpg)

Redis源码地址：https://github.com/redis/redis

Redis在线测试地址(不用下载也能玩)：https://try.redis.io/

Redis命令参考：http://doc.redisfans.com/

## 4.怎么玩

官网文档；

多种数据类型基本操作和配置；

持久化和复制，RDB/AOF

事务的控制

复制，集群等



####$\textcolor{red}{Redis迭代演化和Redis7新特性浅谈}$

版本升级：

![redis历史版本回顾](D:\java学习课件\Redis7\1.Redis入门概述\images\6.redis历史版本回顾.jpg)

```xml
5.0版本是直接升级到6.0版本，对于这个激进的升级，Redis之父antirez表现得很有信心和兴奋，所以第一时间发文来阐述6.0的一些重大功能"Redis 6.0.0 GA is out!":
```

$\textcolor{red}{随后Redis再接再厉，直接王炸Redis7.0---2023年爆款}$

```xml
2022年4月27日Redis正式发布了7.0更新
(其实早在2022年1月31日，Redis已经预发布了7.0rc-1，近过社区的考验后，确认没有重大Bug才会正式发布)
```

Redis版本迭代推演介绍：

​	几个里程碑式的重要版本:如上图：redis历史版本回顾

​	命名规则：Redis从发布至今，已经有十余年的时光了，一直遵循着自己的命名规则:

1. 版本号第二位如果是奇数，则为非稳定版本，如2.7、2.9、3.1
2. $\textcolor{red}{版本号第二位如果是偶数，则为稳定版，如2.6、2.8、3.2}$
3. 当前奇数版本就是下一个稳定版本的开发版，如2.9版本就是3.0版本的开发版本
4. 我们可以通过redis.io官网来下载自己感兴趣的版本进行源码阅读
5. 历史发布版本的源码：https://download.redis.io/releases/




Redis7.0新特性概述：

https://github.com/redis/redis/releases可以查询到历史发布版本，根据7.0-rc1预发布版本，我们可以看到Redis7的新特性：

![](D:\java学习课件\Redis7\1.Redis入门概述\images\7.Redis7新特性.png)

#####部分新特性总览：

2022年4月正式发布的Redis7.0是目前Redis历史版本中变化最大的版本。首先它有超过50个以上的新增命令，其次，它有大量核心特性的新增和改进。

![](D:\java学习课件\Redis7\1.Redis入门概述\images\8.Redis7核心特性概览.png)

1.Redis Functions(目前不用关心)

![](D:\java学习课件\Redis7\1.Redis入门概述\images\9.Redisfunctions.png)

2.Client-eviction

![](D:\java学习课件\Redis7\1.Redis入门概述\images\10.Client-eviction.png)

3.Multi-part AOF

![](D:\java学习课件\Redis7\1.Redis入门概述\images\11.multi-partAOF.png)

4.ACL v2 权限控制

![](D:\java学习课件\Redis7\1.Redis入门概述\images\12.ACLV2.png)

5.新增命令（目前不用关心）

```TEXT
新增ZMPOP，BZMPOP，LMPOP，BLMPOP等新命令，对于EXPIRE和SET命令，新增了更多的命令参数选项。例如，ZMPOP的格式如下：ZMPOP numkeys key [key ...] MIN|MAX [COUNT count],而BZMPOP是ZMPOP的阻塞版本。
```

6.listpack替代ziplist

```text
listpack是用来替代ziplist的新数据结构，在7.0版本已经没有ziplist的配置了（6.0版本仅部分数据类型作为过渡阶段在使用）
```

7.底层性能提升(和编码关系不大)

![](D:\java学习课件\Redis7\1.Redis入门概述\images\13.优化.png)

## 本次将对Redis7的一部分新特性做说明(not all)

## 总体概述

大体和之前的redis版本保持一致和稳定，主要是自身底层性能和**资源利用率上的优化和提高**，如果生产上系统稳定，**不用着急升级到最新redis7版本**，如果从零开始新系统，直接上redis7.0-GA版。

| 多AOF文件支持                           | 7.0 版本中一个比较大的变化就是 aof 文件由一个变成了多个，主要分为两种类型:基本文件(base files)、增量文件(incr files)，请注意这些文件名称是复数形式说明每一类文件不仅仅只有一个。在此之外还引入了一个清单文件(manifest) 用于跟踪文件以及文件的创建和应用顺序(恢复) |
| --------------------------------------- | ------------------------------------------------------------ |
| config命令增强                          | 对于Config Set 和Get命令，支持在一次调用过程中传递多个配置参数。例如，现在我们可以在执行一次Config Set命今中更改多个参数: config set maxmemory 10000001 maxmemory-clients 50% port 6399 |
| 限制客户端内存使用<br />Client-eviction | 一旦 Redis 连接较多，再加上每个连接的内存占用都比较大的时候， Redis总连接内存占用可能会达到maxmemory的上限，可以增加允许限制所有客户端的总内存使用量配置项，redis.config 中对应的配置项<br />//两种配置形式:指定内存大小、基于 maxmemory 的百分比。<br />maxmemory-client 1g<br />maxmemory-client 10% |
| listpack紧凑列表调整                    | listpack 是用来替代 ziplist 的新数据结构，在 7.0 版本已经没有 ziplist 的配置了 (6.0版本仅部分数据类型作为过渡阶段在使用）listpack已经替换了ziplist类似hash-max-ziplist-entries 的配置 |
| 访问安全性增强ACLV2                     | 在redis.conf配置文件中protected-mode默认为yes，只有当你希望你的客户端在没有授权的情况下可以连接到Redis server的时候可以将protect-mode设置为no |
| redis function                          | Redis函数，一种新的通过服务端脚本扩展Redis的方式，函数与数据本身一起存储。简言之，redis自己要去抢夺Lua脚本的饭碗 |
| RDB保存时间调整                         | 将持久化文件RDB的保存规则发生了改变，尤其是时间记录频度变化  |
| 命令新增和变动                          | Zset (有序集合)增加 ZMPOP、BZMPOP、ZINTERCARD 等命令<br />Set (集合)增加 SINTERCARD 命令<br />LIST(列表)增加 LMPOP、BLMPOP ，从提供的键名列表中的第一个非空列表键中弹出一个或多个元素。 |
| 性能资源利用率、安全等改进              | 自身底层部分优化改动，Redis核心在许多方面进行了重构和改进主动碎片整理V2:增强版主动碎片整理，配合Jemalloc版本更新，更快更智能，延时更低<br />HyperLogLog改进:在Redis5.0中，HyperLogLog算法得到改进，优化了计数统计时的内存使用效率，7更加优秀更好的内存统计报告<br />如果不是为了API向后兼容，我们将不再使用slave一词......（政治正确） |

# 三.redis的十大数据类型

## 1.redis字符串（String）

String是redis最基本的数据类型，一个key对应一个value。

string类型是<font color='red'>二进制安全的</font>，意思是redis的string可以包含任何数据，比如jpg图片或者序列化的对象。

string类型是Redis最基本的数据类型，一个redis中字符串value**最多可以是512M**

使用方法：

## 2.redis列表（List）

Redis列表是最简单的字符串列表，按照插入顺序排序。你可以添加一个元素到列表的$\textcolor{blue}{头部（左边）或者尾部（右边）}$，它的底层实际是个$\textcolor{red}{双端链表}$，最多可以包含2^32-1个元素（4294967295，每个列表超过40亿个元素）

## 3.redis哈希表（Hash）

Redis Hash是一个string类型的field（字段）和value（值）的映射表，Hash特别适合用户存储对象。

Redis中每个Hash可以存储2^32-1个键值对（40多亿）

## 4.redis集合（Set）

Redis的Set是string类型的$\textcolor{red}{无序集合}$。集合成员是唯一的，这就意味着集合中不能出现重复的数据，集合对象的编码可以是intset或者Hashtable。

Redis中Set集合是通过哈希表实现的，所以添加，删除，查找的复杂度都是O(1)。

集合中最大的成员数为2^32-1（4294967295，每个集合可存储40多亿个成员）

## 5.redis有序集合（ZSet）

zset(sorted set：有序集合)

Redis zset和Set一样也是string类型元素的集合，且不允许重复的成员。

$\textcolor{red}{不同的是每个元素都会关联一个double类型的分数}$，redis正是通过分数来为集合中的成员进行从小到大的排序。

$\textcolor{red}{zset的成员是唯一的，但是分数（score）却可以重复。}$

$\textcolor{red}{zset集合是通过哈希表实现的，所以添加，删除，查找的复杂度都是O(1)。集合中最大的成员数是2^.32-1}$

## 6.redis地理空间（GEO）

Redis GEO主要用于存储地理位置信息，并对存储的信息进行操作，包括：

添加地理位置的坐标。

获取地理位置的坐标。

计算两个位置之间的距离。

根据用户给定的经纬度坐标来获取指定范围内的地址位置集合。

## 7.redis基数统计（HyperLogLog）

HyperLogLog是用来做$\textcolor{red}{基数统计}$的算法，HyperLogLog的优点是，在输入元素的数量或者体积非常非常大时，计算基数所需要的空间总是固定且是很小的。

在Redis里面，每个HyperLogLog键只需要花费12KB内存，就可以计算接近2^64个不同元素的基数。这和计算基数时，元素越多耗费内存就越多的集合形成鲜明对比。

但是，因为HyperLogLog只会根据输入元素来计算基数，而不会存储输入元素本身，所以HyperLogLog不能像集合那样，返回输入的各个元素。

## 8.redis位图（bitmap）

![](D:\java学习课件\Redis7\3.redis10大数据类型\images\3.redis位图.jpg)

由0和1状态表现的二进制位的bit数组

## 9.redis位域（bitfield）

通过bitfield命令可以一次性操作多个$\textcolor{red}{比特位域(指的是连续的多个比特位)}$，它会执行一系列操作并返回一个响应数组，这个数组中的元素对应参数列表中的相应的执行结果。

说白了就是通过bitfield命令我们可以一次性对多个比特位域进行操作。

## 10.redis流（Stream）

Redis Stream是Redis5.0版本新增加的数据结构。

Redis Stream主要用于消息队列（MQ，Message Queue），Redis本身就是一个Redis发布订阅（pub/sub）来实现消息队列的功能，但它有个缺点就是消息无法持久化，如果出现网络断开、Redis宕机等，消息就会被丢弃。

简单来说发布订阅（pub/sub）可以分发消息，但无法记录历史消息。

而Redis Stream提供了消息的持久化和主备复制功能，可以让任何客户端访问任何时刻的数据，并且能记住每一个客户端的访问位置，还能保证消息不丢失。



$\textcolor{red}{redis常见数据类型操作命令}$

官网英文： https://redis.io/commands/

中文：http://www.redis.cn/commands.html

## Redis键（key）

1. `keys *` :查看库中所有的键

2. `exists` 键名 ：查看某一个键是否存在，返回interger类型

3. `type key` ：查看key的类型

4. `del key`：删除键

5. `unlink`：非阻塞删除，仅仅将keys从keyspace元数据中删除，真正的删除会在后续异步中操作。

   del key 是原子的删除，只有删除成功了才会返回删除结果，如果是删除大key用del会将后面的操作都阻塞，而unlink key 不会阻塞，它会在后台异步删除数据。（**说人话就是del key需要等它慢慢删除，过程中不让别的指令执行，而unlink删除是在后台执行，后台删除过程中可以使用其他指令**）

   > `UNLINK`和`DEL`都是Redis中删除键的指令，但它们有一些区别。
   >
   > 1. 阻塞 vs 非阻塞：`DEL`是阻塞指令，它会立即删除键并阻塞其他命令的执行，直到删除完成。而`UNLINK`是非阻塞指令，它会将键标记为删除，并在后台异步删除键，不会阻塞其他命令的执行。
   > 2. 返回值：`DEL`指令在成功删除键时返回1，如果键不存在则返回0。`UNLINK`指令在成功标记键删除时返回1，如果键不存在则返回0。它们的返回值不同，反映了它们的不同行为。
   > 3. 性能：由于`UNLINK`是非阻塞的，它可以更快地执行，尤其是在删除大量键时。`DEL`指令在删除大量键时可能会阻塞其他操作。
   >
   > 综上所述，如果你需要立即删除键并阻塞其他命令的执行，可以使用`DEL`指令。如果你希望非阻塞地删除键，并且对删除操作的立即结果没有严格要求，可以使用`UNLINK`指令。

6. `ttl key`：查看还有多少秒过期，-1表示永不过期，-2表示已过期

7. `expire key` 秒钟：为给定的key设置过期时间

8. `move key dbindex[0-15]`：将当前数据库的key移动到给定的数据库DB当中

9. `select dbindex`（数字0—15）：切换数据库【0-15】，默认为0

10. `dbsize`：查看当前数据库key的数量

    ```shell
    127.0.0.1:6379> dbsize
    '(integer) 8
    ```

11. `flushdb`：清空当前库

12. `flushall`：通杀全部库

## 11.数据类型命令及落地运用

英文：https://redis.io/commands/

中文：http://www.redis.cn/commands.html

### 11.1

1. 命令不区分大小写，而key是区分大小写的
2. 永远的帮助命令，help @类型
   - help @string
   - help @list
   - help @hash
   - help @hyperloglog

### 11.2Redis字符串(String)

官网：https://redis.io/docs/data-types/strings/

#### 11.2.1最 常 用：set \quad key \quad value  |  get key

![](D:\java学习课件\Redis7\3.redis10大数据类型\images\14.string参数.jpg)

**返回值：**

设置成功则返回OK，返回nil为未执行Set命令，如不满足NX，XX条件等。

若使用GET参数，则返回该键原来的值，或在键不存在时nil。

在java中获得Unix时间

```java
System.out.println(Long.toString(System.currentTimeMillis()/1000L));
```

#### 11.2.2同时设置/获取多个键值’

直接在原来的set上或者get上前面加个m

1. 方法：

```
mset(nx) k1 v1 k2 v2 k3 v3
mget k1 k2 k2
```

**注意**：设置多个键值要么都成功，要么都失败

```shell
127.0.0.1:6379[3]> keys *
1) "k3"
2) "k4"
3) "k2"
127.0.0.1:6379[3]> msetnx k1 v1 k5 v5
(integer) 0
```

#### 11.2.4.获取指定区间范围内的值

getrange/setrange

![](D:\java学习课件\Redis7\3.redis10大数据类型\images\18.getrange和setrange用法.jpg)

### 4.数值增减

$\textcolor{red}{一定要是数据才能进行加减}$

递增数字：INCR key

增加指定的整数：INCRBY key increment

递减数值：DECR key

减少指定的整数：DECRBY key decrement
