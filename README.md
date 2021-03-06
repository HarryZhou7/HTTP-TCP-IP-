HTTP、TCP、IP协议基本定义

HTTP:

　　（HyperText Transport Protocol）是超文本传输协议的缩写，它用于传送WWW方式的数据，关于HTTP协议的详细内容请参考RFC2616。HTTP协议采用了请求/响应模型。

TCP:

　　（Transmission Control Protocol 传输控制协议）是一种面向连接的、可靠的、基于字节流的传输层通信协议，由IETF的RFC 793定义。在简化的计算机网络OSI模型中，它完成第四层传输层所指定的功能，用户数据报协议（UDP）是同一层内 [1]  另一个重要的传输协议。

IP:

　　网络之间互连的协议（IP）是Internet Protocol的外语缩写
　　网络之间互连的协议也就是为计算机网络相互连接进行通信而设计的协议

　　如今的IP网络使用32位地址，以点分十进制表示，如192.168.0.1。
　　地址格式为：IP地址=网络地址+主机地址或 IP地址=网络地址+子网地址+主机地址。
 
tcp/ip基础知识
TCP/IP全称是Transmission Control Protocol/Internet Protocol。 IP地址共32位，4字节。

IP地址分为两部分：网络标识和主机标识。

A类IP地址：第一段为网络标识，剩下三段为主机标识。网络地址最高位必须为零。网络标识长度为7位，主机标识长度为24位。A类网络的主机数最多可以达到1600多台。

B类IP地址：第一、二段位网络标识，第三、四段为主机标识。网络地址最高位必须为10。网络标识长度为14位，主机标识长度位16位。每个网络最多能容纳6万多台主机。

C类IP地址：前三段位网络标识，剩下一段为主机标识。网络地址最高位必须为110。网络标识长度为21位，主机标识长度为8位。每个网络最多容纳254台主机。

子网掩码也是32位的一个IP地址，它的用途是识别本网络内的计算机。两台不同主机的IP地址同时与子网掩码进行AND运算，如果得出结果相同，则说明这两台计算机处于同一个子网内，可以进行直接通信。 域名的构成：主机名＋机构名＋网络名＋最高层域名。
常见面试题

一、Http的报文结构。

（1）HTTP请求报文
一个HTTP请求报文由请求行、请求头部、空行和请求数据4个部分组成，下图是请求报文的一般格式。



 

（2）HTTP响应也由三个部分组成，分别是：状态行、消息报头、响应正文。

二、TCP与UDP的区别。
（1）TCP：面向连接，可靠的，速度慢，效率低。

（2）UDP：无连接、不可靠、速度快、效率高。

当进程需要传输可靠的数据时应使用TCP，当进程需要高效传输数据，可以忽略可靠性时应使用UDP协议。

三、TCP/IP：四层模型。

①网络接口层：对应物理层和数据链路层。

②网络层

③传输层

④应用层：包括会话层、表示层、应用层。

四、HTTP与HTTPS有什么区别？

HTTP协议传输的数据都是未加密的，也就是明文的，因此使用HTTP协议传输隐私信息非常不安全，为了保证这些隐私数据能加密传输，于是网景公司设计了SSL（Secure Sockets Layer）协议用于对HTTP协议传输的数据进行加密，从而就诞生了HTTPS。

简单来说，HTTPS协议是由SSL+HTTP协议构建的可进行加密传输、身份认证的网络协议，要比http协议安全。

HTTPS和HTTP的区别主要如下：

1、https协议需要到ca申请证书，一般免费证书较少，因而需要一定费用。

2、http是超文本传输协议，信息是明文传输，https则是具有安全性的ssl加密传输协议。

3、http和https使用的是完全不同的连接方式，用的端口也不一样，前者是80，后者是443。

4、http的连接很简单，是无状态的；HTTPS协议是由SSL+HTTP协议构建的可进行加密传输、身份认证的网络协议，比http协议安全。

 

五、Ping，ICMP报文是什么。


  PING (Packet Internet Groper)，因特网包探索器，用于测试网络连通性的程序。

  Ping发送一个ICMP(Internet Control Messages Protocol,因特网信报控制协议)；回声请求消息给目的地并报告是否收到所希望的ICMPecho （ICMP回声应答）。

  工作原理：利用网络上机器IP地址的唯一性，给目标IP地址发送一个数据包，再要求对方返回一个同样大小的数据包来确定两台网络机器是否连接相通，时延是多少。

为了提高IP数据报交付成功机会，在网络层使用过了网际控制报文协议（ICMP）来允许主机或路由器报告差错和异常情况。ICMP报文作为IP层数据报的数据，加上数据报首部，组成IP数据报发出去。ICMP协议是IP层协议。

 

六、http1.0与http1.1的区别

1、HTTP 1.0中浏览器与服务器只保持短暂的连接，浏览器的每次请求都与服务器建立一个TCP连接，服务器完成请求处理后立即断开TCP连接，服务器不跟踪每个客户也不记录过去的请求。

2、http1.1提供永久性连接（即1.0使用非持久连接，HTTP1.0没有host的字段).

3、HTTP 1.1中增加Host请求头字段后，实现了在一台WEB服务器上可以在同一个IP地址和端口号上使用不同的主机名来创建多个虚拟WEB站点。

4、http1.1提供身份认证（HTTP1.1提供一个基于口令的基本认证方式，）

 
七、解释一下tcp三次握手四次挥手（对于有网络协议工程师之类笔试,几乎是必考的内容）
TCP三次握手

　　所谓三次握手，是指建立一个TCP连接时，需要客户端和服务器总共发送3个包。

　　三次握手的目的是连接服务器指定端口，建立TCP连接,并同步连接双方的序列号和确认号并交换 TCP 窗口大小信息.在socket编程中，客户端执行connect()时。将触发三次握手。
　　(1) 第一次握手：建立连接时，客户端A发送SYN包(SYN=j)到服务器B，并进入SYN_SEND状态，等待服务器B确认。
 　　(2) 第二次握手：服务器B收到SYN包，必须确认客户A的SYN(ACK=j+1)，同时自己也发送一个SYN包(SYN=k)，即SYN+ACK包，此时服务器B进入SYN_RECV状态。

　　 (3) 第三次握手：客户端A收到服务器B的SYN＋ACK包，向服务器B发送确认包ACK(ACK=k+1)，此包发送完毕，客户端A和服务器B进入ESTABLISHED状态，完成三次握手。

完成三次握手，客户端与服务器开始传送数据。

TCP 四次挥手
　　TCP的连接的拆除需要发送四个包，因此称为四次挥手。客户端或服务器均可主动发起挥手动作，在socket编程中，任何一方执行close()操作即可产生挥手操作。
　　TCP连接是全双工的，因此每个方向都必须单独进行关闭。这原则是当一方完成它的数据发送任务后就能发送一个FIN来终止这个方向的连接。收到一个 FIN只意味着这一方向上没有数据流动，一个TCP连接在收到一个FIN后仍能发送数据。首先进行关闭的一方将执行主动关闭，而另一方执行被动关闭。
（1） TCP客户端发送一个FIN，用来关闭客户到服务器的数据传送。
（2） 服务器收到这个FIN，它发回一个ACK，确认序号为收到的序号加1。和SYN一样，一个FIN将占用一个序号。
（3） 服务器关闭客户端的连接，发送一个FIN给客户端。
（4） 客户端发回ACK报文确认，并将确认序号设置为收到序号加1
 
　　
1. 序列号seq
占4个字节，用来标记数据段的顺序，TCP把连接中发送的所有数据字节都编上一个序号，第一个字节的编号由本地随机产生，给字节编上序号后，就给每一个报文段指派一个序号，序列号seq就是这个报文段中的第一个字节的数据编号。

2. 确认号ack
占4个字节，期待收到对方下一个报文段的第一个数据字节的序号，序列号表示报文段携带数据的第一个字节的编号，而确认号指的是期望接受到下一个字节的编号，因此挡墙报文段最后一个字节的编号+1即是确认号。

3. 确认ACK
占1个比特位，仅当ACK=1，确认号字段才有效。ACK=0，确认号无效。

4. 同步SYN
连接建立时用于同步序号。当SYN=1，ACK=0表示：这是一个连接请求报文段。若同意连接，则在响应报文段中使用SYN=1，ACK=1.因此，SYN=1表示这是一个连接请求，或连接接收报文，SYN这个标志位只有在TCP建立连接才会被置为1，握手完成后SYN标志位被置为0.

5. 终止FIN
用来释放一个

 
SYN攻击
　　在三次握手过程中，服务器发送SYN-ACK之后，收到客户端的ACK之前的TCP连接称为半连接(half-open connect).此时服务器处于Syn_RECV状态.当收到ACK后，服务器转入ESTABLISHED状态.
Syn攻击就是 攻击客户端 在短时间内伪造大量不存在的IP地址，向服务器不断地发送syn包，服务器回复确认包，并等待客户的确认，由于源地址是不存在的，服务器需要不断的重发直 至超时，这些伪造的SYN包将长时间占用未连接队列，正常的SYN请求被丢弃，目标系统运行缓慢，严重者引起网络堵塞甚至系统瘫痪。
Syn攻击是一个典型的DDOS攻击。检测SYN攻击非常的方便，当你在服务器上看到大量的半连接状态时，特别是源IP地址是随机的，基本上可以断定这是一次SYN攻击.在Linux下可以如下命令检测是否被Syn攻击
netstat -n -p TCP | grep SYN_RECV
一般较新的TCP/IP协议栈都对这一过程进行修正来防范Syn攻击，修改tcp协议实现。主要方法有SynAttackProtect保护机制、SYN cookies技术、增加最大半连接和缩短超时时间等.
但是不能完全防范syn攻击。
