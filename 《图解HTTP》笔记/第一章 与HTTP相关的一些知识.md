## 第一章 与HTTP相关的一些知识

#### 一、HTTP版本历史  
> 1990 -- 0.9版

> 1996 -- 1.0版 

> 1997 -- 1.1版

#### 二、TCP/IP
> TCP/IP是互联网相关的各类协议族的总称，比如从电缆的规格到IP地址的选定等等。
> <img width = "449" height = "365" src = media/14909466245648/14923999006687.jpg>


_**TCP/IP的4个层次**_

_**应用层**_  ---  主要解决如何包装数据的（HTTP/DNS/FTP都属于应用层的子集）。

> 关于HTTP协议与TCP/IP的关系，网上有这么一段话很容易理解。
> 我们在传输数据时，可以只使用TCP/IP（传输层）而不用应用层，但如果那样的话便无法识别数据内容。如果想要传输的数据有意义，就必须使用到应用层协议；

_**传输层**_  ---  提供处于网络连接中的两台计算机之间的数据传输。
> 传输层有两个性质不同的协议，TCP和UDP。
> TCP(Transmission Control Protocol): 为了更容易传递大数据，把数据分割且能够通过三次握手策略来确认数据最终是否送到到对方。
> UDP(User Data Protocol): UDP不是面向连接的，UDP传输数据前并不与对方建立连接，对方接收到数据后也不发确认信号。所以说UDP是无连接、不可靠但传输速度快的一种数据传输协议。

_**网络层**_  ---  网络层用来处理网络上流动数据包，该层规定了通过怎样的路径达到对方计算机，并把数据包传送给对方。
> IP协议（并非IP地址）属于该层的协议，IP协议的作用就是把各种数据包传送给对方。而满足传送到对方的两个最重要条件就是IP地址和MAC地址。
> IP地址，是指目的地节点的地址。
> MAC地址，是指网咖所属的固定地址。
> 没有人能全面掌握互联网中的传输状况，客户端通常指掌握服务器的IP地址和下一个路由器的MAC地址。类似快递系统，先将快递发往集散中心，集散中心来检查送货地址并明确下站该送往哪个区域。IP地址类似收货方地址，MAC地址类似快递中转站地址。

_**链路层**_  ---  用来处理连接网络的硬件部分，硬件上的范畴均在链路层的作用范围内。

#### 三、Socket
Socket是对TCP/IP协议的封装，Socket本身并不是协议而是一个调用接口。
> TCP/IP只是一个协议栈，就想操作系统的运行机制一样，必须要具体实现而同时还要提供对外的操作接口。TCP/IP也要提供可供程序员做网络开发所用的接口，Socket就是这个接口。

#### 四、DNS(Domain Name System)
DNS服务是和HTTP协议一样位于应用层的协议，它提供域名到IP地址之间的解析服务（www.google.com与20X.189.1X3之间的相互转化的服务）。

<img width = "460" height = "314" src = media/14909466245648/14923999985977.jpg>

#### 五、HTTP请求过程
1. **[客户端]** 将网址给DNS；
2. **[DNS]** 将网址解析成IP地址并传回客户端；
3. **[HTTP协议]** 生成HTTP请求报文；
4. **[TCP协议]** 将HTTP请求报文分割成报文段；
5. **[IP协议]** 搜索对方地址，边中转边传送；
6. **[TCP协议]** 接收到报文段，重新组装；
7. **[HTTP协议]** 处理请求内容；
8. **[服务器]** 接收到HTTP请求；

##### 如图
<img width="409" height = "611" src = media/14909466245648/14914684358740.jpg>

#### 六、URI和URL
URI可以表示互联网某一域，也可以表示互联网某一资源，而URL只能表示一个资源，可见URL是URI的子集。


