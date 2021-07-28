# Windows网络编程

## TCP/IP协议

Transmission Control Protocol/Internet Protocol

基于tcp/ip协议的c/s模型

### 概念

tcp/ip协议族，并不是tcp协议和ip协议的总称，tcp/ip指的是整个网络传输体系。

<img src=".images/image-20210610185449112-1627435898392439.png" alt="image-20210610185449112" style="zoom:67%;" />

### tcp/ip协议的特点

<font color=red>面向连接的，看可靠的，基于字节流的传输层协议。</font>



udp/ip:面向非连接的，不可靠的，基于数据报的传输层协议。





### clicent/server 客户端/服务器模型

QQ客户端，向腾讯服务器请求数据

**c/s模型其实的概念层面的，实现层面可以是基于任何的网络协议**

b/s模型 浏览器  一对多，一个客户端对应多个服务器（如打开不同网页）  基于http/https协议



**套接字编程与socket编程**

socket和套接字编程统称网络编程





## 服务端 

### 网络头文件和网路库

最底层的网络函数

#### #include<WinSock2.H>



### 打开网络库 int WSAStartup

#### 功能

打开网络库/启动网络库，库里的函数/功能才能使用

w windows

s socket

a Asynchronous 异步

startup 启动

```
同步：堵塞/卡死状态  执行完才能继续进行下一个
异步：多个工作同时进行
```

#### 参数

[WSAStartup function (winsock.h) - Win32 apps | Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/api/winsock/nf-winsock-wsastartup)

当看到参数有LPP前缀的时候，是说我们这里要传对应类型变量的地址，这是win32API的规则

<img src=".images/image-20210610201326223-1627435901753440.png" alt="image-20210610201326223" style="zoom:67%;" />



#### 返回值

![image-20210610203935828](.images/image-20210610203935828-1627435903080441.png)

<img src=".images/image-20210610210836198-1627435904407442.png" alt="image-20210610210836198" style="zoom:80%;" />



### 校验版本

![image-20210610211510875](.images/image-20210610211510875-1627435905754443.png)



kj





### 创建SOCKET

[socket function (winsock2.h) - Win32 apps | Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/api/winsock2/nf-winsock2-socket)

#### 什么是socket

将底层复杂协议体系，执行流程，进行了封装，封装完的结果，就是一个socket了。

也就是说，SOCKET是我们调用协议进行通信的操作接口



#### 意义

将复杂的协议过程与我们编程人员分开，我们直接操作一个简单的SOCKET就行了，对于底层的协议过程细节，完全不用知道。



#### 本质

SOCKET就是一个类型

![image-20210610212823503](.images/image-20210610212823503-1627435908774445.png)![image-20210610212840483](.images/image-20210610212840483-1627435907688444.png)



![image-20210610212724226](.images/image-20210610212724226-1627435909953446.png)



![image-20210610213236440](.images/image-20210610213236440-1627435914071447.png)

**就是一个协议号**



#### 应用

![image-20210610213543873](.images/image-20210610213543873-1627435915271448.png)



#### 使用

<img src=".images/image-20210611130607736-1627435916584449.png" alt="image-20210611130607736" style="zoom: 80%;" />

##### 参数1

**地址类型**

![image-20210611131334354](.images/image-20210611131334354-1627435917695450.png)





#####  参数2

**套接字类型**

数据传递方式

![image-20210611153224545](.images/image-20210611153224545-1627435919255451.png)



##### 参数3

**协议的类型**

![image-20210611153526880](.images/image-20210611153526880-1627435921152452.png)







##### 返回值

![image-20210611154222558](.images/image-20210611154222558-1627435922703453.png)

![image-20210611154231390](.images/image-20210611154231390-1627435924087454.png)

<img src=".images/image-20210611154329221-1627435925823455.png" alt="image-20210611154329221"  />





### 绑定地址与端口 int bind

![image-20210615101143473](.images/image-20210615101143473-1627435927799456.png)

![image-20210611155935102](.images/image-20210611155935102-1627435930048457.png)

#### 参数

##### 参数2

![image-20210611163302988](.images/image-20210611163302988-1627435930935458.png)

[sockaddr - Win32 apps | Microsoft Docs](https://docs.microsoft.com/zh-cn/windows/win32/winsock/sockaddr-2)

<img src=".images/image-20210615102231205-1627435932455459.png" alt="image-20210615102231205" style="zoom: 67%;" />



![image-20210615104902932](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210615104902932.png)

![image-20210611161434794](.images/image-20210611161434794-1627435936151460.png)

![image-20210611162020958](.images/image-20210611162020958-1627435937840461.png)

![image-20210611162050955](.images/image-20210611162050955-1627435939144462.png)



[in_addr (winsock2.h) - Win32 apps | Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/api/winsock2/ns-winsock2-in_addr)



#### 返回值

![image-20210611170337424](.images/image-20210611170337424-1627435940632463.png)

![image-20210611170742056](.images/image-20210611170742056-1627435941855464.png)





### 开始监听int WSAAPI listen

[listen function (winsock2.h) - Win32 apps | Microsoft Docs](https://docs.microsoft.com/zh-cn/windows/win32/api/winsock2/nf-winsock2-listen)



#### 作用

将套接字置于正在侦听传入连接的状态

**如果作为一个服务器，在调用socket()、bind()之后就会调用listen()来监听这个socket，如果客户端这时调用connect()发出连接请求，服务器端就会接收到这个请求。**

![image-20210615164247100](.images/image-20210615164247100-1627435945055465.png)

#### 使用

**listen函数的第一个参数即为要监听的socket描述字，第二个参数为相应socket可以排队的最大连接个数。socket()函数创建的socket默认是一个主动类型的，listen函数将socket变为被动类型的，等待客户的连接请求。**

![image-20210615110126580](.images/image-20210615110126580-1627435946414466.png)



#### 返回值



### 创建客户端socket SOCKET WSAAPI accept

#### 作用

允许在套接字上进行传入连接尝试。

![image-20210615161955396](.images/image-20210615161955396-1627435948607467.png)

**TCP服务器端依次调用socket()、bind()、listen()之后，就会监听指定的socket地址了。TCP客户端依次调用socket()、connect()之后就向TCP服务器发送了一个连接请求。TCP服务器监听到这个请求之后，就会调用accept()函数取接收请求，这样连接就建立好了。之后就可以开始网络I/O操作了，即类同于普通文件的读写I/O操作。**



#### 参数

![image-20210615165922071](.images/image-20210615165922071-1627435949831468.png)



#### accept调试

##### 堵塞，同步

这个函数是阻塞的，没有客户端链接，那就一直卡在这儿，等着。

##### 多个链接

一次只能一个，5个就要5个次循环





### 与客户端收发消息 int recv/send







#### recv函数

![image-20210615204602776](.images/image-20210615204602776-1627435951592469.png)

##### 作用和原理

![image-20210615190721386](.images/image-20210615190721386-1627435952903470.png)

##### 参数

![image-20210615190908529](.images/image-20210615190908529-1627435953799471.png)





###### 参数4

 **0**![image-20210615201154277](.images/image-20210615201154277-1627435955271472.png)



**MESG_PEEK**

![image-20210615201413325](.images/image-20210615201413325-1627435956328473.png)

读取不删，每次recv相同



**MSG_OOB**

**![image-20210615202909283](.images/image-20210615202909283-1627435957280474.png)**



**MSG_WAITALL**

![image-20210615203134513](.images/image-20210615203134513-1627435958784475.png)



##### 返回值

![image-20210615191625515](.images/image-20210615191625515-1627435959799476.png)





#### send函数

![image-20210615185857871](file://C:/Users/10592/AppData/Roaming/Typora/typora-user-images/image-20210615185857871.png?lastModify=1623761160)

##### 作用

![image-20210615204750996](.images/image-20210615204750996-1627435964832477.png)

##### 参数2

![image-20210615210753766](.images/image-20210615210753766-1627435966001478.png)











## 客户端

<img src=".images/image-20210615211849696-1627435967928479.png" alt="image-20210615211849696" style="zoom: 67%;" />



### int connect函数

![image-20210615213423488](.images/image-20210615213423488-1627435969182480.png)





## 5种Windows的网络模型

### Select模型

#### 特点

![image-20210617185912661](.images/image-20210617185912661-1627435970480481.png)





#### 服务端

![image-20210617185952071](.images/image-20210617185952071-1627435971671482.png)



#### 逻辑

![image-20210617190027361](.images/image-20210617190027361-1627435972766483.png)





#### 定义一个装客户端socket结构

![image-20210617190218088](.images/image-20210617190218088-1627435973869484.png)





#### Select函数

![image-20210617191611872](.images/image-20210617191611872-1627435975382485.png)

##### 作用

![image-20210617190532834](.images/image-20210617190532834-1627435977039486.png)

##### 参数

参数2：

服务器：accept

客户端：接受客户端的rece 

![image-20210617191529889](.images/image-20210617191529889-1627435978735487.png)





参数3：检查send

![image-20210617192400857](.images/image-20210617192400857-1627435980011488.png)



 参数4、5

![image-20210617195139329](.images/image-20210617195139329-1627435981080489.png)

