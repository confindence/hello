### WriteUp

#### 1.题目名称

cookie

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

X老师告诉小宁他在cookie里放了些东西，小宁疑惑地想：‘这是夹心饼干的意思吗？’

![1564990688599](C:\Users\Administrator\Desktop\05-20190805-cookie\WriteUp\images\1564990688599.png)

http://111.198.29.45:32704/

#### 5.解题步骤

##### 	5.1打开网址

![1564990743090](C:\Users\Administrator\Desktop\05-20190805-cookie\WriteUp\images\1564990743090.png)

##### 		5.2 查看cookie

页面提示cookie，查看网页cookies（js代码查看cookie方法：document.cookie）

![1564990867211](C:\Users\Administrator\Desktop\05-20190805-cookie\WriteUp\images\1564990867211.png)

##### 5.3查看cookie.php

尝试访问cookie.php

![1564990973272](C:\Users\Administrator\Desktop\05-20190805-cookie\WriteUp\images\1564990973272.png)

##### 5.4查看响应头

页面提示看http响应，查看响应头

![1564991124475](C:\Users\Administrator\Desktop\05-20190805-cookie\WriteUp\images\1564991124475.png)

#### 6.flag值

cyberpeace{1da8952f015744909ddf26b421c5b67c}

#### 7.延伸

HTTP协议是无状态的协议。一旦数据交换完毕，客户端与服务器端的连接就会关闭，再次交换数据需要建立新的连接。这就意味着服务器无法从连接上跟踪会话。为了分辨链接是谁发起的，采用cookie和session技术。

**Cookie通过在客户端记录信息确定用户身份**，**Session通过在服务器端记录信息确定用户身份**。

- cookie：

  cookie是浏览器保存在用户电脑上的一小段文本，用来保存用户在网站上的必要的信息。Web页面或服务器告诉浏览器按照一定的规范存储这些信息，并且在以后的所有请求中，这些信息就会自动加在http请求头中发送给服务器，服务器根据这些信息判断不同的用户。并且cookie本身是安全的。

  客户端请求服务器，如果服务器需要记录该用户状态，就使用response向客户端浏览器颁发一个Cookie。客户端浏览器会把Cookie保存起来。当浏览器再请求该网站时，浏览器把请求的网址连同该Cookie一同提交给服务器。服务器检查该Cookie，以此来辨认用户状态。服务器还可以根据需要修改Cookie的内容。

- session：

  session的作用和cookie差不多，也是用来解决Http协议不能维持状态的问题。session保存在服务器上。客户端浏览器访问服务器的时候，服务器把客户端信息以某种形式记录在服务器上。不会在网络中进行传输，所以session较cookie而言更安全。

  session是依赖cookie的，当用户访问某一站点时，服务器会为这个用户产生唯一的session_id,并把这个session_id以cookie的形式发送到客户端，以后的客户端的所有请求都会自动携带这个cookie（前提是浏览器支持并且没有禁用cookie）。

  session工作机理：

  ![img](http://www.phpfensi.com/uploadfile/2016/0830/20160830022704117.png)

Cookie并不提供修改、删除操作。如果要修改某个Cookie，只需要新建一个同名的Cookie，添加到response中覆盖原来的Cookie。

如果要删除某个Cookie，只需要新建一个同名的Cookie，并将maxAge设置为0，并添加到response中覆盖原来的Cookie。注意是0而不是负数。负数代表其他的意义。

注意：修改、删除Cookie时，新建的Cookie除value、maxAge之外的所有属性，例如name、path、domain等，都要与原Cookie完全一样。否则，浏览器将视为两个不同的Cookie不予覆盖，导致修改、删除失败。