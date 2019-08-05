### WriteUp

#### 1.题目名称

weak_auth

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

小宁写了一个登陆验证页面，随手就设了一个密码。

![1564996277907](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564996277907.png)

http://111.198.29.45:42081/

#### 5.解题步骤

##### 	5.1 打开网址

![1564996334658](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564996334658.png)

##### 		5.2 查看源码

![1564996511969](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564996511969.png)

无有效信息

##### 5.3尝试登陆

随便输入用户名和密码，页面出现please login as admin，说明用户名是admin

![1564996635023](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564996635023.png)

查看源码，提示要字典，使用burpsuit爆破

![1564996744101](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564996744101.png)

5.4使用burpsuit爆破

![1564996924101](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564996924101.png)

当密码是123456时长度不一样，输入得到flag值

![1564997046896](C:\Users\Administrator\Desktop\09-20190805-weak_auth\WriteUp\images\1564997046896.png)

#### 6.flag值

cyberpeace{02897fa3ed7ea12cd8600c5b625ca258}

#### 7.延伸

弱密码是易于猜测的密码，主要有以下几种：

 1. 顺序或重复的字相邻字母： “111111” 、“abcdefg”、 “asdf”、“qwer”键盘上的
 2. 使用数字或符号的仅外观类似替换，例如使用数字“1”、“0”替换英文字母“i”、“O”，字符“@”替换字母“a”等；
 3. 登录名的一部分：密码为登录名的一部分或完全和登录名相同；
 4. 常用的单词：如自己和熟人的名字及其缩写，常用的单词及其缩写，宠物的名字等；
 5. 常用数字：比如自己或熟人的生日、证件编号等，以及这些数字与名字、称号等字母的简单组合。

爆破字典：https://github.com/rootphantomer/Blasting_dictionary