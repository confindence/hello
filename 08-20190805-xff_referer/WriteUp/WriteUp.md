### WriteUp

#### 1.题目名称

xff_referer

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

X老师告诉小宁其实xff和referer是可以伪造的。

![1564994389622](C:\Users\Administrator\Desktop\08-20190805-xff_referer\WriteUp\images\1564994389622.png)

http://111.198.29.45:54550/

#### 5.解题步骤

##### 	5.1 打开网址

![1564994448121](C:\Users\Administrator\Desktop\08-20190805-xff_referer\WriteUp\images\1564994448121.png)

##### 		5.2 修改ip地址

页面提示ip地址必须为123.123.123.123，利用burpsuit抓包修改ip地址

![1564994703125](C:\Users\Administrator\Desktop\08-20190805-xff_referer\WriteUp\images\1564994703125.png)

##### 5.3修改referer

修改ip地址后，网页提示必须来自谷歌浏览器，修改Referer

![1564994786068](C:\Users\Administrator\Desktop\08-20190805-xff_referer\WriteUp\images\1564994786068.png)

![1564995309271](C:\Users\Administrator\Desktop\08-20190805-xff_referer\WriteUp\images\1564995309271.png)

#### 6.flag值

cyberpeace{2aad675bc150fd8ed2445a4b50465290}

#### 7.延伸

X-Forwarded-For

- 是一个 HTTP 扩展头部，主要是为了让 Web 服务器获取访问用户的真实 IP 地址。在代理转发及反向代理中经常使用X-Forwarded-For 字段。

- 是用来识别通过HTTP代理或负载均衡方式连接到Web服务器的客户端最原始的IP地址的HTTP请求头字段。简单地说，xff是告诉服务器当前请求者的最终ip的http请求头字段，通常可以直接通过修改http头中的X-Forwarded-For字段来仿造请求的最终ip

- https://www.cnblogs.com/huaxingtianxia/p/6369089.html

- 产生背景

  ![1564046571235](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1564046571235.png)

- ![1564046444984](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1564046444984.png)

代理

- 正向代理

  正向代理是一个位于客户端【用户A】和原始服务器(origin server)【服务器B】之间的服务器【代理服务器Z】，为了从原始服务器取得内容，用户A向代理服务器Z发送一个请求并指定目标(服务器B)，然后代理服务器Z向服务器B转交请求并将获得的内容返回给客户端。

  作用：1. 访问本无法访问的服务器B

  ​			2.加速访问服务器B

  ​			3.Cache作用

  ​			4.客户端访问授权

  ​			5.隐藏访问者的行踪

- 反向代理

  反向代理正好与正向代理相反，对于客户端而言代理服务器就像是原始服务器，并且客户端不需要进行任何特别的设置。客户端向反向代理的命名空间(name-space)中的内容发送普通请求，接着反向代理将判断向何处(原始服务器)转交请求，并将获得的内容返回给客户端。

  作用：1、保护和隐藏原始资源服务器

  ​			2、负载均衡

- 透明代理

  透明代理的意思是客户端根本不需要知道有代理服务器的存在，它改编你的request fields（报文），并会传送真实IP。注意，加密的透明代理则是属于匿名代理，意思是不用设置使用代理了。

https://blog.csdn.net/championhengyi/article/details/80671517

Referer

- ![1564048304815](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1564048304815.png)
- 作用：防止盗链；计算网页上的链接访问量
- 比如在一个网页里面插入一个超链接，链接到其他的网页，那么当点击这个超链接从而链接到另外一个页面的时候，相当于浏览器向 web 服务器发送了一个 http 请求，对于另外一个页面而言，这个 referer 就是上一个页面的 URL，而对于从地址栏里面直接输入 URL 或者是刷新网页的方式，则 referer = null，通过设置这个 referer 可以防止盗链的问题。