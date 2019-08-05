### WriteUp

#### 1.题目名称

simple_js

#### 2.难度系数

简单

#### 3.题目来源

root-me

#### 4.题目描述

小宁发现了一个网页，但却一直输不对密码。(Flag格式为 Cyberpeace{xxxxxxxxx} )

![1564992260787](C:\Users\Administrator\Desktop\07-20190805-simple_js\WriteUp\images\1564992260787.png)

http://111.198.29.45:40012/

#### 5.解题步骤

##### 	5.1 打开网址

![1564992307887](C:\Users\Administrator\Desktop\07-20190805-simple_js\WriteUp\images\1564992307887.png)

##### 		5.2查看源代码

![1564992375344](C:\Users\Administrator\Desktop\07-20190805-simple_js\WriteUp\images\1564992375344.png)

通过观察js代码发现dechiffre()函数实现的功能是将一串用逗号分隔的数字即已经赋值的pass按ascii转成字符串，得到字符串FAUX PASSWORD HAHA。但有一行16进制数，转为ascii得到flag值

![1564993632803](C:\Users\Administrator\Desktop\07-20190805-simple_js\WriteUp\images\1564993632803.png)

![1564993671341](C:\Users\Administrator\Desktop\07-20190805-simple_js\WriteUp\images\1564993671341.png)

#### 6.flag值

cyberpeace{786OsErtk12}

#### 7.延伸

split() 方法用于把一个字符串分割成字符串数组。

语法：stringObject.split(separator,howmany)

参数:

separator:字符串或正则表达式，从该参数指定的地方分割 stringObject

howmany:该参数可指定返回的数组的最大长度

String.fromCharCode():实现 ascii码转字符