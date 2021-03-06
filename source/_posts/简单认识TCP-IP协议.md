title: 简单认识TCP/IP协议
author: yql
tags:
  - TCP/IP
categories:
  - 计算机基础
date: 2018-11-24 14:35:00
---
![TCP/IP](https://i.loli.net/2018/12/29/5c2767be3570e.jpg) 
  前言：简单认识TCP/IP，不涉及具体的理论. 
  <!--more-->
   
 ##### 什么是TCP/IP
 > 互联网协议（Internet Protocol Suite）是一个网络通信模型，以及一整个网络传输协议家族，为互联网的基础通信架构。它常被通称为TCP/IP协议族（英语：TCP/IP Protocol Suite，或TCP/IP Protocols），简称TCP/IP.它也常被视为是简化的七层OSI模型.  
  
  下面这张图左边是OSI模型，右边是TCP/IP协议.
 
 
 
 
 ![图一](https://i.loli.net/2018/12/29/5c2768063023f.png)

##### 为什么会有TCP/IP
> 在世界上各地，各种各样的电脑运行着各自不同的操作系统为大家服务，这些电脑在表达同一种信息的时候所使用的方法是千差万别。就好像圣经中上帝打乱了各地人的口音，让他们无法合作一样。计算机使用者意识到，计算机只是单兵作战并不会发挥太大的作用。只有把它们联合起来，电脑才会发挥出它最大的潜力。于是人们就想方设法的用电线把电脑连接到了一起。  
但是简单的连到一起是远远不够的，就好像语言不同的两个人互相见了面，完全不能交流信息。因而他们需要定义一些共通的东西来进行交流，TCP/IP就是为此而生。TCP/IP不是一个协议，而是一个协议族的统称。里面包括了IP协议，IMCP协议，TCP协议，以及我们更加熟悉的http、ftp、pop3协议等等。电脑有了这些，就好像学会了外语一样，就可以和其他的计算机终端做自由的交流了。


##### 具体层次介绍
> 1.网络访问层:物理层是定义物理介质的各种特性,如：机械特性电子特性，功能特性，规程特性.网络访问层(Network Access Layer)在TCP/IP参考模型中并没有详细描述，只是指出主机必须使用某种协议与网络相连。  




> 2.网络层: 负责相邻计算机之间的通信.网络层(Internet Layer)是整个体系结构的关键部分，其功能是使主机可以把分组发往任何网络，并使分组独立地传向目标。这些分组可能经由不同的网络，到达的顺序和发送的顺序也可能不同。高层如果需要顺序收发，那么就必须自行处理对分组的排序。互联网层使用因特网协议(IP，Internet Protocol)。TCP/IP参考模型的互联网层和OSI参考模型的网络层在功能上非常相似。  

> 3.传输层: 提供应用程序间的通信。传输层(Tramsport Layer)使源端和目的端机器上的对等实体可以进行会话。在这一层定义了两个端到端的协议：传输控制协议(TCP，Transmission Control Protocol)和用户数据报协议(UDP，User Datagram Protocol)。TCP是**面向连接**的协议,它提供可靠的报文传输和对上层应用的连接服务。为此，除了基本的数据传输外，它还有可靠性保证、流量控制、多路复用、优先权和安全性控制等功能。UDP是**面向无连接**的不可靠传输的协议，主要用于不需要TCP的排序和流量控制等功能的应用程序。  

 
 

> 4.应用层(Application Layer)包含所有的高层协议，包括：  
1.虚拟终端协议(TELNET，TELecommunications NETwork),允许一台机器上的用户登录到远程机器上，并进行工作  
2.文件传输协议(FTP，File Transfer Protocol),提供有效地将文件从,用于电子邮件的收发；  
4.域名服务(DNS，Domain Name Service),用于把主机名映射到网络地址；   
5.网上新闻传输协议(NNTP，Net News Transfer Protocol)、,用于新闻的发布、检索和获取；  
6.超文本传送协议(HTTP，HyperText Transfer Protocol)等,用于在WWW上获取主页。 
 

  
 
  
###### 一些基础知识  
> ###### 一.关于传输层有TCP与UDP两种协议  


1. 面向有连接型和面向无连接型的区别：  
_①  TCP面向有接型：![](https://i.loli.net/2018/12/29/5c276807bf2e1.png)
发送数据之前，需要在收发主机之间建立一条通信线路，在通信传输前后，专门进行建立和断开连接的处理，如果与对端之间无法通信，可避免发送无谓的数据。即三次握手与四次挥手.网上搜索的,大多涉及专业知识，可以通过这个[故事](https://blog.csdn.net/violet_echo_0908/article/details/51440509)认识三次握手。

  _②  UDP面向无接型：![](https://i.loli.net/2018/12/29/5c2768069114d.png)  
这种类型不要求建立和断开连接，发送端可任何时候发送数据，接收端也不知道自己何时从哪里接受数据，这种情况下，接收端需要时常确认是否收到数据，彼此也不需要确认对方是否存在.   


2  优缺点：  
 
  _① TCP：

优点：可靠、稳定

TCP的可靠体现在TCP在传输数据之前，会有三次握手来建立连接，而且在数据传递时，有确认、窗口、重传、拥塞控制机制，在数据传完之后，还会断开连接用来节约系统资源

缺点：慢，效率低，占用系统资源高，易被攻击

在传递数据之前要先建立连接，这会消耗时间，而且在数据传递时，确认机制、重传机制、拥塞机制等都会消耗大量时间，而且要在每台设备上维护所有的传输连接。然而，每个链接都会占用系统的CPU、内存等硬件资源。因为TCP有确认机制、三次握手机制，这些也导致TCP容易被利用，实现DOS、DDOS、CC等攻击.  

_②UDP：

优点：快,比TCP稍安全

UDP没有TCP拥有的各种机制，是一个无状态的传输协议，所以传递数据非常快，没有TCP的这些机制，被攻击利用的机制就少一些，但是也无法避免被攻击

缺点：不可靠，不稳定

因为没有TCP的那些机制，UDP在传输数据时，如果网络质量不好，就会很容易丢包，造成数据的缺失

 

适用场景：

TCP：当对网络通讯质量有要求时，比如HTTP、HTTPS、FTP等传输文件的协议， POP、SMTP等邮件传输的协议

UDP：对网络通讯质量要求不高时，要求网络通讯速度要快的场景.                                                      



 > ###### 二.关于应用层中的端口port  
 
"端口"是英文port的意译，可以认为是设备与外界通讯交流的出口。端口可分为**虚拟端口**和**物理端口**，其中虚拟端口指计算机内部或交换机路由器内的端口，不可见。例如计算机中的80端口、21端口、23端口等。物理端口又称为接口。是可见端口，计算机背板的RJ45网口，交换机路由器集线器等RJ45端口。电话使用RJ11插口也属于物理端口的范畴。  

物理端口就不写了,说下应用层中的虚拟端口。
 >> 端口的作用：我们知道，一台拥有IP地址的主机可以提供许多服务，比如Web服务、FTP服务、SMTP服务等，这些服务完全可以通过1个IP地址来实现。那么，主机是怎样区分不同的网络服务呢？显然不能只靠IP地址，因为IP 地址与网络服务的关系是一对多的关系。实际上是通过“IP地址+端口号”来区分不同的服务的。  
 
 
 


## 总结
 
 
![](https://i.loli.net/2018/12/29/5c2768ed9e65a.png)