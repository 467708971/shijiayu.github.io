# 浅析URL
## URL所包含部分及作用
URL包含：协议 + 域名或IP + 端口号 + 路径 + 查询字符串 + 锚点  
* 协议：  
&emsp;&emsp;用于传输超媒体文档（例如 HTML）的应用层协议，提供对Web 浏览器与 Web 服务器之间的通信的支持

* 域名/IP：  
&emsp;&emsp;域名是在 互联网 的网站的地址，被用于 URL 识别一个服务器属于哪个特定的网站  
&emsp;&emsp;IP是分配给连接到使用Internet协议的网络的每个设备的一串数字，用于定位一台设备

* 端口号：  
&emsp;&emsp;每个服务都有一个对应的号码，这个号码就叫端口号

* 路径：  
&emsp;&emsp;用于在同一级域名中请求不同的界面

* 查询字符串：  
&emsp;&emsp;用于在同一个页面显示不同的内容

* 锚点：  
&emsp;&emsp;用于在不同的位置处看到同一个内容

## DNS作用及nslookup命令的使用
&emsp;&emsp;DNS (Domain Name System) 域名系统，是一个层次化、分散化的Internet连接资源命名系统，其维护着一个包含域名与对应资源例如IP地址的列表  
其中DNS最突出的作用是：将易于记忆的域名翻译成数字化的IP地址    

nslookup：显示可用于诊断域名系统 (DNS) 基础结构的信息  
nslookup使用方法：  
```
nslookup [exit | finger | help | ls | lserver | root | server | set | view] [options]
```

## IP的作用及ping命令的使用
&emsp;&emsp;Internet Protocal主要约定了两件事：关于如何定位一台设备以及关于如何封装数据报文以跟其他设备交流

ping命令：通过向另一台 TCP/IP 计算机发送 Internet 控制消息协议 (ICMP) 回响请求消息来验证 IP 级连接，显示相应的回响回复消息以及往返时间  
具体使用方法：  
```
ping [/t] [/a] [/n <count>] [/l <size>] [/f] [/I <TTL>] [/v <TOS>] [/r <count>] [/s <count>] [{/j <hostlist> | /k <hostlist>}] [/w <timeout>] [/R] [/S <Srcaddr>] [/4] [/6] <targetname>
```

## 域名是什么及域名的分类
域名就是对IP的别称，一个域名可以对多个IP，一个IP也可以对不同域名，域名和IP通过DNS对应

域名分为：顶级域名、二级域名、三级域名  
如 www.baidu.com  
其中com是顶级域名；  
baidu.com是二级域名；  
www.baidu.com是三级域名；
它们是父子关系