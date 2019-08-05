### WriteUp

#### 1.题目名称

get_post

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

X老师告诉小宁同学HTTP通常使用两种请求方法，你知道是哪两种吗？

![1564987302774](C:\Users\Administrator\Desktop\02-20190805-get_post\WriteUp\images\1564987302774.png)

http://111.198.29.45:56253/

#### 5.解题步骤

##### 	5.1 打开网址

![1564987365497](C:\Users\Administrator\Desktop\02-20190805-get_post\WriteUp\images\1564987365497.png)

##### 		5.2 get提交

根据页面提示用get方式提交变量，即在原url后添加/?a=1,出现新页面

![1564987639575](C:\Users\Administrator\Desktop\02-20190805-get_post\WriteUp\images\1564987639575.png)

##### 5.3 post提交

使用HackBar插件来提交数据

![1564987700006](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1564987700006.png)

得到flag值

![1564987788917](C:\Users\Administrator\Desktop\02-20190805-get_post\WriteUp\images\1564987788917.png)

#### 6.flag值

cyberpeace{1b22163b7a6e84a12eede09ac66c3807}

#### 7.延伸

```
HTTP协议中共定义了八种方法或者叫“动作”来表明对Request-URI指定的资源的不同操作方式，具体介绍如下：

GET：向特定的资源发出请求。GET请求的数据会附在URL之后（数据放在HTTP协议头中），以？分割URL和传输数据，数据之间用&相连如：login.action?name=hyddd&password=idontknow&verify=%E4%BD%A0%E5%A5%BD。如果数据是英文字母/数字，原样发送，如果是空格，转换为+，如果是中文/其他字符，则直接把字符串用BASE64加密，得出如：%E4%BD%A0%E5%A5%BD，其中％XX中的XX为该符号以16进制表示的ASCII。

POST：向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中（HTTP包的包体中）。POST请求可能会导致新的资源的创建和/或已有资源的修改。

OPTIONS：返回服务器针对特定资源所支持的HTTP请求方法。也可以利用向Web服务器发送'*'的请求来测试服务器的功能性。

HEAD：向服务器索要与GET请求相一致的响应，只不过响应体将不会被返回。这一方法可以在不必传输整个响应内容的情况下，就可以获取包含在响应消息头中的元信息。

PUT：向指定资源位置上传其最新内容。

DELETE：请求服务器删除Request-URI所标识的资源。

TRACE：回显服务器收到的请求，主要用于测试或诊断。

CONNECT：HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。
```

