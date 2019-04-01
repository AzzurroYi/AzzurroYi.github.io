title: HTTP与HTTPS
author: yql
tags:
  - HTTPS
categories:
  - 计算机基础
date: 2018-11-23 23:40:00
---
![HTTPS](https://i.loli.net/2018/12/29/5c276805c5d63.jpg)
 
 
 <!--more-->



###### 前言：在是大一计算机菜鸡对HTTPS一些浅显了解，有不对的地方欢迎指正。   
##### 什么是HTTPS
HTTPS（全称：Hyper Text Transfer Protocol over Secure Socket Layer），是以安全为目标的HTTP通道，简单讲是HTTP的安全版。即HTTP下加入SSL层，HTTPS的安全基础是SSL，因此加密的详细内容就需要SSL。 现在它被广泛用于万维网上安全敏感的通讯，例如交易支付方面。  

##### HTTP和HTTPS之间的区别
 > 1. HTTP 是明文传输，HTTPS 通过 SSL\TLS 进行了加密
 > 2. HTTP 的端口号是 80，HTTPS 是 443
 > 3. HTTPS 需要到 CA 申请证书，一般免费证书很少，需要交费
 > 4. HTTPS 的连接很简单，是无状态的；HTTPS 协议是由 SSL+HTTP 协议构建的可进行加密传输、身份认证的网络协议，比 HTTP 协议安全。  

##### 为什么要使用HTTPS
> 1. 建立一个信息安全通道，来保证数据传输的安全
> 2. 确认网站的真实性，防止钓鱼网站 
    
    
    
  在看HTTPS时，百度时都是一些专业的术语，对于一个大一学生，对这些什么应用层、传输层的协议和各种服务器的信息都不是很了解，所以看也看不明白，于是看到一篇文章：[一个故事讲完HTTPS](https://mp.weixin.qq.com/s/StqqafHePlBkWAPQZg3NrA)
  /(ㄒoㄒ)/~~算是有个大概的理解了