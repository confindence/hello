### WriteUp

#### 1.题目名称

simple_php

#### 2.难度系数

1.0

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

小宁听说php是最好的语言,于是她简单学习之后写了几行php代码。

![1564999882109](C:\Users\Administrator\Desktop\12-20190805-simple_php\WriteUp\images\1564999882109.png)

http://111.198.29.45:57287/

#### 5.解题步骤

##### 	5.1 打开网址

![1564999925572](C:\Users\Administrator\Desktop\12-20190805-simple_php\WriteUp\images\1564999925572.png)

##### 		5.2 分析代码

如果a==0且a有一个值，输出flag1，如果b只为数字或数字字符串，则会退出，如果b>1234且由不是数字字符串，则输出flag2。所以构造：?a=0a&b=12345a

![1565000740668](C:\Users\Administrator\Desktop\12-20190805-simple_php\WriteUp\images\1565000740668.png)

#### 6.flag值

Cyberpeace{647E37C7627CC3E4019EC69324F66C7C}

#### 7.延伸

==  中等式：等式两侧数值相同即可，变量类型不强制相同。（PHP是弱语言）

`===` 恒等式：等式两侧不仅需要数值相同，变量类型也需要相同。

**is_numeric()** 函数用于检测变量是否为数字或数字字符串。