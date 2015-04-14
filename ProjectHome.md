Jsession是纯java编写的用于java web集群的软件，它分为服务器端和客户端，服务器端叫SessionBox,用于保存session，Session是保存在内存中。客户端叫SessionClient,用于Session的负载均衡并与服务器端通信，通信框架用nio的Netty,有着极高的性能，通讯协议使用了Protocol Buffers,应用程序操作Session同传统方式一样，没有特殊性，简化编程.

JSession是Shared Nothing Architecture架构，是一种无共享的Session服务集群方式，架设集群极其简单，容易扩展。SessionBox服务器可以集群，因此不会存在Session服务器的单点问题,当要组建大规模集群系统时只要的是增加应用服务器和SessionBox服务器。

Jsession特性



&lt;1&gt;

SessionBox和sessionClient纯java编写，SessionBox?的安装极其简单.



&lt;2&gt;

SessionBox与SessionClient的通信是使用java nio的Netty,有极高的性能。



&lt;3&gt;

web服务器对Session的set,get操作只针对其属性数据，而不是整个Session的数据，减少了数据传输量，提高性能。



&lt;4&gt;

SessionBox集群方式在客户端，不存在单点故障问题。


JSession让java web集群变得如此简单!