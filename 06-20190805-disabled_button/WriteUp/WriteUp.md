### WriteUp

#### 1.题目名称

disabled_button

#### 2.难度系数

简单

#### 3.题目来源

 Cyberpeace-n3k0

#### 4.题目描述

X老师今天上课讲了前端知识，然后给了大家一个不能按的按钮，小宁惊奇地发现这个按钮按不下去，到底怎么才能按下去呢？

![1564991811202](C:\Users\Administrator\Desktop\06-20190805-disabled_button\WriteUp\images\1564991811202.png)

http://111.198.29.45:58314/

#### 5.解题步骤

##### 	5.1 打开网址

![1564991857513](C:\Users\Administrator\Desktop\06-20190805-disabled_button\WriteUp\images\1564991857513.png)

##### 		5.2 查看源代码

![1564991911759](C:\Users\Administrator\Desktop\06-20190805-disabled_button\WriteUp\images\1564991911759.png)

发现form表单中的按钮有disabed属性，尝试删除试试，得到flag值

![1564991988563](C:\Users\Administrator\Desktop\06-20190805-disabled_button\WriteUp\images\1564991988563.png)

#### 6.flag值

cyberpeace{2e7f8692421e0f17571cda498347534e}

#### 7.延伸

disabled属性

```
disabled 属性规定应该禁用 input 元素。

被禁用的 input 元素既不可用，也不可点击。可以设置 disabled 属性，直到满足某些其他的条件为止（比如选择了一个复选框等等）。然后，就需要通过 JavaScript 来删除 disabled 值，将 input 元素的值切换为可用。

注释：disabled 属性无法与 <input type="hidden"> 一起使用。
```

语法

```
<input disabled="value">
```

