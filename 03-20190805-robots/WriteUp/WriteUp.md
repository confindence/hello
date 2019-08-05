### WriteUp

#### 1.题目名称

robots

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

X老师上课讲了Robots协议，小宁同学却上课打了瞌睡，赶紧来教教小宁Robots协议是什么吧。

![1564988887155](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1564988887155.png)

http://111.198.29.45:44532/

#### 5.解题步骤

##### 	5.1打开网址

![1564989014662](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1564989014662.png)

显示空白页面

##### 		5.2 查看源代码

![1564989063436](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1564989063436.png)

没有任何信息，题目提示robots协议，尝试访问网站根目录下的robots.txt文件

![1564989130225](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1564989130225.png)

页面提示一个文件，flag_1s_h3re.php,访问得到答案

![1564989216018](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1564989216018.png)

#### 6.flag值

cyberpeace{0bbf1b712ae77e81ef32a5d3bcaa63d5}

#### 7.延伸

![1564989301936](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1564989301936.png)

![](C:\Users\Administrator\Desktop\03-20190805-robots\WriteUp\images\1563896907851.png)

robots支持使用通配符"*"和"$"来模糊匹配url：

"$" 匹配行结束符。

"*" 匹配0或多个任意字符。