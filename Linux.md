# Linux

## 第1章 Linux基础

### 1.Linux介绍

#### 1.2一些名词

GNU:号召软件自由

GPL:公共许可证

FSF:自由软件基本会，给GNU提供资金支持

POSIX:一套标准，度UI系统调用的服务接口进行标准化



#### 1.3Linux发行版

debian->Ubuntu 

![image-20210701214352043](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701214352043.png)

![image-20210701214508178](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701214508178.png)

redhat->CentOS



#### 1.4Linux内核

​	

```
Linux 系统从应用角度来看，分为内核空间和用户空间两个部分。内核空间是 Linux 操作系统的主要部分，但是仅有内核的操作系统是不能完成用户任务的。丰富并且功能强大的应用程序包是一个操作系统成功的必要件。这个和武林秘籍一样，不仅得有招式还得有内功心法。

Linux 的内核主要由 5 个子系统组成：进程调度、内存管理、虚拟文件系统、网络接口、进程间通信。下面将依次讲解这 5 个子系统。
```

![](https://subingwen.cn/linux/version-path/kernel.jpg)







### 2.Linux目录

#### 2.1 Linux目录结构

![image-20210701220005305](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701220005305.png)

#### 2.2相对路径

./：代表目前所在的目录，也可以用.表示

../：代表当前目录的上一次目录，也可以使用..表示

### 3.命令解析器

#### 3.1工作原理

![image-20210701222320325](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701222320325.png)

<img src="C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701222211150.png" alt="image-20210701222211150" style="zoom:150%;" />



#### 3.2命令提示行



<img src="C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701221355734.png" alt="image-20210701221355734" style="zoom:50%;" />

~：当前用户的家目录

$:当前用户的身份

![image-20210701221540392](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701221540392.png)

root：当前用户，可以用whoami查看

VM-4-7-ubuntu：主机名

/home：当前路径

#：root用户



#### 3.3命令行快捷键

![image-20210701222533939](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210701222533939.png)





## 第2章 文件管理命令

### 1.cd命令

cd 使用相对路径/绝对目录

cd==cd ~   进入当前用户家目录

两个目录间的快速切换： cd -





### 2.ls命令

![image-20210703102403004](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703102403004.png)

#### 2.1显示所有文件

ls -a：显示隐藏的文件

ls -l：显示文件的详细信息

ls -F：显示目录，如果是文件夹将会在后面加/

ls -h：在显示文件大小的时候以一种直观的方式

![image-20210703102854430](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703102854430.png)

#### 2.2显示文件详细信息

##### 2.2.1文件类型

![image-20210703103143028](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703103143028.png)

![image-20210703103351913](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703103351913.png)



##### 2.2.2用户类型 

Linux有三大用户：文件所有者，文件所属用户组，其他人

![image-20210703104000706](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703104000706.png)

##### 2.2.3文件权限

一共四种权限：

读权限：r表示 ->read

写权限：w表示->write

执行权限：x表示->excute

没有任何权限：用-表示

![image-20210703104921215](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703104921215.png)

<font color=red>从第二个字母起，3个3个一组，共三组，分别表示 文件所有者，文件所属组用户，其他人的权限</font>

<font color=blue>只有对目录有执行权限，才能打开目录</font>



##### 2.2.4硬链接计数

![image-20210703105344582](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703105344582.png)

**其实就是文件别名**



##### 2.2.5其他属性

![image-20210703105443807](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703105443807.png)

robin：文件所属者

robin：文件所属组用户

4.0k：文件的大小，若文件是目录，4.0k仅代表目录所占空间，不包含目录内文件的内容

May 12 2020：文件的修改日期



### 3.创建删除目录  

![image-20210703105927861](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703105927861.png)

创建单层目录 

<img src="C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703110035816.png" alt="image-20210703110035816" style="zoom:200%;" />



创建多层级目录要加 -p

![image-20210703111217366](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703111217366.png)

![image-20210703111553704](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703111553704.png)





rmdir：只能删除单目录，内部不能包括子目录

![image-20210703111757776](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703111757776.png) 



rm:

![image-20210703112516234](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703112516234.png)

![image-20210703112538998](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703112538998.png)

![image-20210703112758131](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703112758131.png)

### 4.cp命令

**拷贝文件**

![image-20210703121033565](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210703121033565.png)

![image-20210704125431765](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704125431765.png)





**拷贝目录**

![image-20210704125514689](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704125514689.png)

![image-20210704125904226](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704125904226.png)

![image-20210704130111693](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704130111693.png)

![image-20210704130628177](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704130628177.png)





### 5.mv命令

**文件的移动**

![image-20210704131517267](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704131517267.png)

![image-20210704131428544](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704131428544.png)





**文件的改名**

![image-20210704132120328](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704132120328.png)

![image-20210704132145687](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704132145687.png)



**文件覆盖**

![image-20210704132240835](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704132240835.png)

 

<img src="C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704132546083.png" alt="image-20210704132546083"  />





### 6.查看文件内容

**cat：**

![image-20210704155659700](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704155659700.png)



**more：**

![image-20210704160054891](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210704160054891.png)

  

**less：**

![image-20210705161444690](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705161444690.png)



**head：**

![image-20210705161644966](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705161644966.png)

![image-20210705161706820](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705161706820.png)





**tail：**

![image-20210705161740955](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705161740955.png)

![image-20210705161839450](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705161839450.png)





### 7.链接的创建

![image-20210705162254808](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705162254808.png)



**软连接：**

语法：  ln -s 源文件路径<font color=red>(绝对路径)</font> 软连接文件的名字（可以带路径）

![image-20210705172140697](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705172140697.png)

![image-20210705172522951](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705172522951.png)

![image-20210705172326580](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705172326580.png)





**硬链接：**

语法：  ln  源文件名称  硬连接文件的名字（可以带路径） <font color=green>**不允许给目录创建硬链接**</font>

![image-20210705173526170](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210705173526170.png)



### 8.文件属性

#### 8.1修改文件权限

![image-20210706193757419](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706193757419.png)

**chmod：change mod**



**文字设定法：**

chmod who(=/+/-)rwx 文件名  

**who: u(user),g(group),o(other),a(all)**

```
比如 chmod a=rwx b.txt

比如 chmod o-wx a/

比如 chmod go-wx b.txt
```

![image-20210706195048633](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706195048633.png)





**数字设定法：**

![image-20210706200938759](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706200938759.png)

```
例如 chmod 777 b.txt

例如 chmod -200 b.txt
```





#### 8.2修改文件所有者 

**chown**

![image-20210706202150052](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706202150052.png)



sudo：让普通用户使用管理员权限成功执行这条指令

普通用户拥有sudo权限需要授权：

![image-20210706203211295](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706203211295.png)





#### 8.3修改文件所属组

**chgrp**

![image-20210706202737753](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706202737753.png)



### 9.其他命令

#### 9.1tree命令

![image-20210706203335680](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706203335680.png)

![image-20210706203445912](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706203445912.png)



#### 9.2pwd命令

无参数  **pwd查看当前用户的工作目录**



#### 9.3touch命令

![image-20210706204300476](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706204300476.png)

![image-20210706204516595](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706204516595.png)

b文件已经存在，touch b，b的内容没有改变，修改时间变了



#### 9.4which命令

![image-20210706204754295](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706204754295.png)

查看命令所在的目录







#### 9.5重定向命令

![image-20210706205211613](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706205211613.png)

echo==printf![image-20210706205925006](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210706205925006.png)

**abcd覆盖了hello world！**

**可以通过 >> 符号进行追加避免这种现象**









## 第3章 用户管理指令

 

### 1.切换用户

![image-20210709150616045](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709150616045.png)

![image-20210709152217726](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709152217726.png)



### 2.添加删除用户

![image-20210709152915172](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709152915172.png)

#### 2.1添加新用户

**sudo useradd 用户名**

```
# 添加用户
# sudo -> 使用管理员权限执行这个命令
$ sudo adduser 用户名

# centos
$ sudo useradd 用户名

# ubuntu
$ sudo useradd -m -s /bin/bash  用户名

# 在使用 adduser 添加新用户的时候，有的Linux版本执行完命令就结束了，有的版本会提示设置密码等用户信息
robin@OS:~/Linux$ sudo adduser lisi
Adding user `lisi' ...
Adding new group `lisi' (1004) ...
Adding new user `lisi' (1004) with group `lisi' ...
Creating home directory `/home/lisi' ...
Copying files from `/etc/skel' ...
Enter new UNIX password: 
Retype new UNIX password: 
passwd: password updated successfully
Changing the user information for lisi
Enter the new value, or press ENTER for the default
        Full Name []: 
        Room Number []: 
        Work Phone []: 
        Home Phone []: 
        Other []: 
Is the information correct? [Y/n] y
```





#### 2.2删除用户

**sudo userdel 用户名 -r** 

![image-20210709160948759](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709160948759.png)





### 3.添加删除用户组

**sudo groupadd 组名**

![image-20210709162629474](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709162629474.png)

![image-20210709163143175](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709163143175.png)





### 4.修改密码

![image-20210709164704403](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709164704403.png)

![image-20210709164809728](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709164809728.png)

![image-20210709164924613](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210709164924613.png)







## 第4章 压缩命令

![image-20210710205906088](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710205906088.png)

### 1.tar

![image-20210710210411978](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710210411978.png)

tar不能压缩，但可以打包文件(多合一)

gzip和bzip可以压缩文件，但不可以打包文件





#### 1.1压缩(.tar.gz/ .tgz  .tar.bz2 )



![image-20210710210923521](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710210923521.png)

![image-20210710210845167](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710210845167.png)



![image-20210710211518220](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710211518220.png)



#### 1.2解压缩(.tar.gz/.tgz .tar.bz2 )

![image-20210710212737739](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710212737739.png)

![image-20210710213345343](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710213345343.png)

![image-20210710213444420](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210710213444420.png)



### 2.zip

![image-20210711095324242](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711095324242.png)

#### 2.1压缩(.zip)

![image-20210711100137264](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711100137264.png)

![image-20210711100434311](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711100434311.png)



#### 2.2解压缩(.zip)

![image-20210711100841542](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711100841542.png)

![image-20210711101057501](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711101057501.png)





### 3.rar

![image-20210711101858796](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711101858796.png)

#### 3.1压缩(.rar)

![image-20210711102313958](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711102313958.png)

![image-20210711112448915](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711112448915.png)





#### 3.2解压缩(.rar)

![image-20210711122826507](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210711122826507.png)

### 4.xz

![image-20210712211129367](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210712211129367.png)

#### 4.1压缩(.tar.xz)

![image-20210712211225689](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210712211225689.png)

![image-20210712211455861](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210712211455861.png)



**tar cvf xxx.tar 要压缩的文件**

**xz -z xxx.tar**

![image-20210712211604634](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210712211604634.png)

#### 4.2解压缩(.tar.xz)

![image-20210712211909885](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210712211924272.png)

**xz -d xxx.tar.xzz**

**tar xvf xxx.tar** 

![image-20210712212241803](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210712212241803.png)

















### 第5章 查找命令

![image-20210713155257023](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713155257023.png)

#### 1.find

![image-20210713155606006](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713155606006.png)

##### 1.1文件名(-name)

<font color=red>**find  搜索路径 -name 要搜索的文件名**</font>

![image-20210713155915130](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713155915130.png)

![image-20210713160012807](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713160012807.png)

![image-20210713160255402](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713160255402.png)



##### 1.2文件类型(type)

![image-20210713160341568](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713160341568.png)

<font color=red>**find  搜索路径 -type 文件类型**</font>

![image-20210713160505713](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713160505713.png)





##### 1.3文件大小(-size)

![image-20210713161704195](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713161704195.png)

<font color=red>**find  搜索路径 -size 文件大小**</font>

![image-20210713161855993](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713161855993.png)

![image-20210713161949896](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713161949896.png)

![image-20210713162429641](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713162429641.png)





##### 1.4目录层级

![image-20210713162809324](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713162809324.png)

![image-20210713163043022](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713163043022.png)



##### 1.5同时执行多个操作

###### 1.5.1exec

![image-20210713165724584](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713165724584.png)

<font color=red>**find  搜索路径 参数 参数值 -exec shell命令2 {} \\；**</font>

![image-20210713181127293](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713181127293.png)

###### 1.5.2ok

**交互命令**

![image-20210713190458057](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713190458057.png)

<font color=red>**find  搜索路径 参数 参数值 -ok shell命令2 {} \\；**</font>

![image-20210713190751007](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713190751007.png)



###### 1.5.3xargs

![image-20210713191713076](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713191713076.png)

<font color=red>**find  搜索路径 参数 参数值 |xargs shell命令2 {} \\；**</font>

![image-20210713191927726](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713191927726.png)

![image-20210713192841114](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713192841114.png)

xargs  √ 

exec ×





#### 2.grep

![image-20210713193031835](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713193031835.png)

<font color=red>**grep '搜索的内容' 搜索的路径/文件 参数 **</font>

![image-20210713193659975](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713193659975.png)

 

####  3.locate

**不是直接检索文件**

**而是检索数据库的内容，数据库中含有本地所有文件信息**

![image-20210713194949365](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713194949365.png)



<font color=red>**sudo updatedb **</font>

![image-20210713195810980](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713195810980.png)

![image-20210713195950573](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713195950573.png)

 

![image-20210713200319739](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713200319739.png)

![image-20210713201314817](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713201314817.png)

![image-20210713201335652](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713201335652.png)







## 第6章 vim的使用

### 1.vim的安装

![image-20210713205455344](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713205455344.png)

![image-20210713205714299](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713205714299.png)

![image-20210713205742879](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713205742879.png)

![image-20210713205837191](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713205837191.png)





### 2.vim的模式

![](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713210122783.png)





### 3.命令模式下的操作

![image-20210713211345504](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713211345504.png)



#### 3.1保存退出

![image-20210713211446800](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713211446800.png)

#### 3.2代码格式化

![image-20210713211518320](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713211518320.png)



#### 3.3光标移动

![image-20210713211714014](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713211714014.png)

![image-20210713212010582](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713212010582.png)

```
home/0：行首

end/shift+4：行尾

gg：第一行行首

G：最后一行行首

nG：跳转到第n行行首 （n用键盘上方数组表示）

n+回车：光标位置向下移动n行的行首
```





#### 3.4删除命令

![image-20210713214132565](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210713214132565.png)





#### 3.5撤销和反撤销

![image-20210714095526977](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210714095526977.png)





#### 3.6复制和粘贴

 

![image-20210715163011906](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715163011906.png)





#### 3.7可视模式

v：version

![image-20210715164008368](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715164008368.png)

![image-20210715164302347](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715164302347.png)

![image-20210715164318830](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715164318830.png)

##### 3.7.1字符可视模式



![image-20210715165848720](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715165848720.png)

##### 3.7.2行可视模式

![image-20210715165924967](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715165924967.png)

##### 3.7.3块可视化模式

![image-20210715165948005](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715165948005.png)



##### 3.7.4代码注释

![image-20210715170716167](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715170716167.png)

 

#### 3.8替换

r:replace

![image-20210715171318314](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715171318314.png)



#### 3.9查找 

![image-20210715192143792](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715192143792.png)

 **记得/ 后加回车**

#号：光标指向单词  然后按#

![image-20210715194319816](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715194319816.png)





#### 3.10查看man文档



![image-20210715194539327](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715194539327.png)

例如：man 1 cp

![image-20210715195237034](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715195237034.png)





#### 3.11切换到编辑模式

![image-20210715200011536](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715200011536.png)





### 4.末行模式下的操作

#### 4.1命令模式到末行模式

![image-20210715203303922](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715203303922.png)

![image-20210715203403540](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715203403540.png)

![image-20210715203508795](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715203508795.png)



#### 4.2保存退出

![image-20210715203558788](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715203558788.png)



#### 4.3替换 



<font color=red>**:%s/被替换文字/新关键字/g**</font>

![image-20210715204553729](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715204553729.png)



#### 4.4末行模式下的分屏操作

![image-20210715210805836](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715210805836.png)



![image-20210715211720926](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715211720926.png)

ctrl+w+w 选定窗口->  ：q/wq



#### 4.5行跳转

![image-20210715212141860](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715212141860.png)

#### 4.5执行shell命令

![image-20210715212240592](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715212240592.png)

![image-20210715212350272](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715212350272.png)



### 5.vim配置文件

![image-20210715212634580](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210715212634580.png)

















## 第7章 GCC

**GNU Compiler Collection**



### 1.安装GCC

![image-20210717212552278](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717212552278.png)

 

### 2.gcc工作流程

![image-20210717213100854](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717213100854.png)

![img](https://subingwen.cn/linux/gcc/gcc.jpg)

源文件->预处理文件

![image-20210717213647819](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717213647819.png)



预处理->汇编

![image-20210717214011362](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717214011362.png)



汇编->二进制

![image-20210717214439886](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717214439886.png)

 

二进制->可执行程序

![image-20210717214914559](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717214914559.png)



**执行可执行程序 ：./+可执行程序名字**

![image-20210717215033708](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717215033708.png)



**源文件->可执行程序**

![image-20210717215500240](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717215500240.png)



未指定名字的情况下：

![image-20210717215908711](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717215908711.png)





### 3.gcc常用参数

![image-20210717221312507](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210717221312507.png)

#### 3.1指定生成的文件名(-o)

![image-20210718101807478](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718101807478.png)

#### 3.2搜索头文件

![image-20210718102032266](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718102032266.png)

**同时编译多个文件用通配符 *.c**





![image-20210718102236904](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718102236904.png) 

 





#### 3.3指定一个宏(-D)



![image-20210718103119982](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718103119982.png)

![image-20210718103029459](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718103029459.png)

![image-20210718103157564](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718103157564.png)





### 4.多文件编译

#### 4.1准备工作

![image-20210718104409130](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718104409130.png)

#### 4.2编译运行

![image-20210718104449132](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718104449132.png)

### 5.gcc与g++

![image-20210718105402549](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718105402549.png)

![image-20210718105924570](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718105924570.png)

![image-20210718110420724](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718110420724.png)

![image-20210718105755300](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718105755300.png)



## 第8章 静态库和动态库

![image-20210718111425326](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718111425326.png)



### 1.静态库

![image-20210718112023233](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718112023233.png)

![image-20210718112250310](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718112250310.png)

#### 1.1生成静态链接库

具体步骤如下：

1.需要将源文件进行汇编，得到.o文件，需要使用参数-c

![image-20210718112638387](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718112638387.png)



2.将得到的.o进行打包，得到静态库

![image-20210718113301759](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718113301759.png)

![image-20210718113321532](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718113321532.png)



3.发布头文件和静态库：head.h和libcalc.a

![image-20210718151739793](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718151739793.png)



#### 1.2静态库的使用

![image-20210718152602889](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718152602889.png)

![image-20210718152644847](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718152644847.png)

![image-20210718152812972](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718152812972.png)





### 2.动态库

![image-20210718153524145](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718153524145.png)

#### 2.1生成动态链接库

![image-20210718154156210](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718154156210.png)

![image-20210718154402703](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718154402703.png)

 

1.![image-20210718154829259](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718154829259.png)

2.

![image-20210718154914156](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718154914156.png)

3.

![image-20210718161644280](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718161644280.png)

 

#### 2.2动态库的使用

![image-20210718162501808](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718162501808.png)

![image-20210718162524927](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718162524927.png)

#### 2.3解决动态库无法加载的问题

#####  2.3.1库的工作原理

![image-20210718164318325](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718164318325.png)

##### 2.3.2动态链接器

<font color=red>**☆☆☆☆☆☆**</font>

![image-20210718164725116](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718164725116.png)

#####  2.3.3解决方案

**查看环境变量**

![image-20210718171349197](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718171349197.png)



**添加环境变量**(只对当前终端有效)

![image-20210718172253178](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718172253178.png)

![image-20210718172915123](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718172915123.png)



管理员权限

![image-20210718173238228](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718173238228.png)



管理员权限

![image-20210718173248592](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718173248592.png)

##### 2.3.4验证

![image-20210718173541595](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718173541595.png)

**查看可执行程序需要的库文件**

![image-20210718170826611](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718170826611.png)





### 3.优缺点

#### 3.1静态库

![image-20210718205435388](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718205435388.png)

#### 3.2动态库

![image-20210718205729630](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210718205729630.png)





## 第9章 Makefile

![image-20210720201654314](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210720201654314.png)



![image-20210720201746079](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210720201746079.png)

### 1.规则

![image-20210720202022677](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210720202022677.png)

![image-20210720202142272](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210720202142272.png)



![image-20210720202222337](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210720202222337.png)

```
app：目标

a.c b.c c.c ：原材料(依赖)

		（Tab）+gcc a.c b.c d.c -o app：命令
```







### 2.工作原理

#### 2.1规则的执行

![image-20210722163448456](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210722163448456.png)

```
# makefile
# 规则之间的嵌套
# 规则1
app:a.o b.o c.o
	gcc a.o b.o c.o -o app
# 规则2
a.o:a.c
	gcc -c a.c
# 规则3
b.o:b.c
	gcc -c b.c  
# 规则4
c.o:c.c
	gcc -c c.c
```

![image-20210722163911582](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210722163911582.png)



#### 2.2文件的时间戳

![image-20210722165734383](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210722165734383.png)



#### 2.3自动推导

使用命令 make 编译扩展名为.c 的 C 语言文件的时候，源文件的编译规则不用明确给出。这是因为 make 进行编译的时候会使用一个默认的编译规则，按照默认规则完成对.c 文件的编译，生成对应的.o 文件。它使用命令 cc -c 来编译.c 源文件。在 Makefile 中只要给出需要构建的目标文件名（一个.o 文件），make 会自动为这个.o 文件寻找合适的依赖文件（对应的.c 文件），并且使用默认的命令来构建这个目标文件。

![image-20210722170200318](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210722170200318.png)

**.o文件不存在，自动推导.c文件生成.o文件**

![image-20210722170305598](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210722170305598.png)







![image-20210722173639467](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210722173639467.png)





### 3.变量

![image-20210723100450265](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723100450265.png)



#### 3.1自定义变量

![image-20210723100613908](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723100613908.png)

![image-20210723101632791](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723101632791.png)



#### 3.2预定义变量

![image-20210723104229235](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723104229235.png)

![image-20210723110158901](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723110158901.png)



#### 3.3自动变量

![image-20210723110504920](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723110504920.png)

![image-20210723110618209](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723110618209.png)

**最常用 $@ $^ $<**

![image-20210723110904003](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723110904003.png)

$^==add.o dov.o main.o mult.o sub.o

$@==calc





### 4.模式匹配

![image-20210723111630628](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723111630628.png)

![image-20210723111943300](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210723111943300.png)

![image-20210724102454624](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724102454624.png)





### 5.函数

![image-20210724102653127](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724102653127.png)

#### 5.1wildcard

![image-20210724103126433](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724103126433.png)



#### 5.2patsubst

![image-20210724103522278](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724103522278.png)

![image-20210724103702368](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724103702368.png)

#### 5.3函数练习

![image-20210724104920404](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724104920404.png)

![image-20210724105247693](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724105247693.png)

#### 5.4make clean

![image-20210724111508480](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724111508480.png)

![image-20210724111546276](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724111546276.png)

为了防止上面命令执行失败，后面命令终止执行，可以在指令前加 -

比如：![image-20210724111852292](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724111852292.png)











## 第10章 GDB调试

![image-20210724144450343](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724144450343.png)

### 1.调试准备

**-g**

![image-20210724144701697](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724144701697.png)

![image-20210724144758366](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724144758366.png)

![image-20210724152019853](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152019853.png)





### 2.启动和退出gdb

#### 2.1启动gdb

**gdb 文件名**

![image-20210724152119520](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152119520.png)

![image-20210724152204947](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152204947.png)



#### 2.2命令行传参

![image-20210724152501030](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152501030.png)

![image-20210724152536681](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152536681.png)



#### 2.3gdb中启动程序

```
run：到断点处停，无断点直接跑完

start：阻塞在main函数第一行，等待其他gdb命令
```

![image-20210724152648205](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152648205.png)

![image-20210724152717352](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152717352.png)

#### 2.4退出gdb

```
q/quit
```

![image-20210724152749489](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152749489.png)



### 3.查看代码

#### 3.1当前文件

```
l/list

l 行号

l函数名
```

![image-20210724152924472](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724152924472.png)

**如果进行了文件切换，切换到哪个文件，哪个文件就是当前文件**

 

![image-20210724153333865](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724153333865.png)





#### 3.2 切换文件

```
l 文件名(a.cpp):行号/函数名
```

![image-20210724153932374](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724153932374.png)

![image-20210724154920417](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724154920417.png)



#### 3.3设置显示的行数

```
set list/listsize x
show list/listsize 
```

![image-20210724155355641](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724155355641.png)

![image-20210724155437531](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724155437531.png)

listsize==list





### 4.断点操作

#### 4.1设置断点

```
break/b 行号
break/b 函数名
break/b 文件名(a.cpp):行号
break/b 文件名(a.cpp):函数名
break/b 位置参数 if 变量==x(条件断点，多用于循环)
```

![image-20210724160420629](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724160420629.png)

![image-20210724160735189](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724160735189.png)

#### 4.2 查看断点

```
info break
i b
```

![image-20210724162503896](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724162503896.png)

![image-20210724162528861](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724162528861.png)





#### 4.3删除断点

```
delete/del/d 断点序号
delete/del/d 断点序号 断点序号 断点序号...
delete/del/d 断点序号-断点序号
```

![image-20210724162940180](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724162940180.png)

![image-20210724163101952](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724163101952.png)





#### 4.4设置断点状态

```
disable/dis 断点序号
disable/dis 断点序号 断点序号 断点序号...
disable/dis 断点序号-断点序号

enable/ena 断点序号
enable/ena 断点序号 断点序号 断点序号...
enable/ena 断点序号-断点序号
```

![image-20210724163345629](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724163345629.png)

![image-20210724163440163](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724163440163.png)

![image-20210724163720765](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724163720765.png)

![image-20210724163837543](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724163837543.png)





### 5.调试命令



#### 5.1继续运行gdb

```
continue/c
```

![image-20210724171256117](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724171256117.png)



#### 5.2手动打印信息

```
p/print 变量名
```

![image-20210724171414628](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724171414628.png)

![image-20210724171445662](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724171445662.png)

![image-20210724172509202](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724172509202.png)



####  5.3自动打印信息 

##### 5.3.1 设置变量名自动显示

```
display 变量名
```

![image-20210724200431841](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724200431841.png)

##### 5.3.2查看自动显示列表

```
info/l display
```

![image-20210724200619556](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724200619556.png)

![image-20210724200947994](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724200947994.png)



##### 5.3.3取消自动显示

```
undisplay/delete 变量序号 
undisplay/delete 变量序号 变量序号 变量序号...
undisplay/delete 变量序号-变量序号
```

![image-20210724201042598](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724201042598.png)

![image-20210724201100961](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724201100961.png)

![image-20210724201156293](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724201156293.png)

```
disable display  变量序号  
disable display  变量序号 变量序号 变量序号...
disable display  变量序号-变量序号

enable display  变量序号  
enable display  变量序号 变量序号 变量序号...
enable display  变量序号-变量序号
```



#### 5.4单步调试

##### 5.4.1 step

```
start后
step/s
```

**逐步调试，会进入函数体内部**

![image-20210724205245020](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724205245020.png)



##### 5.4.2 finish

```
finish
```

![image-20210724205538622](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724205538622.png)

##### 5.4.3 next

```
next/n
```

**不会进入函数体内部进行逐步调试**

![image-20210724205408098](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724205408098.png)



##### 5.4.4until

```
#循环的开始/末尾 直接跳出循环
until
```

**不能有断点，循环体的开始行或结束行执行命令**![image-20210724210645642](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724210645642.png)



#### 5.5设置变量值

```
set var 变量名=x
```

![image-20210724211025962](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210724211025962.png)

