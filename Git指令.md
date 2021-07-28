



# Git的使用

## 1.本地仓库

### 1.1组成

![image-20210727135231650](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727135231650.png)



工作流程：

![image-20210727135207424](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727135207424.png)



### 1.2本地仓库操作

![image-20210727135837927](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727135837927.png)

![image-20210727135856897](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727135856897.png)



![image-20210727140004081](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727140004081.png)

a.创建空目录

![image-20210727140222087](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727140222087.png)

 

b.进入目录



c.Git仓库的初始化

**指令：git init**

![image-20210727140724374](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727140724374.png)



![image-20210727141156561](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727141156561.png)

![image-20210727141330192](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727141330192.png)

后续操作，重复使用git add和git commit即可。

**如果更改文件内容，git add 文件名，git commit -m "修复了...的bug"**



### 1.3时光穿梭机--版本回退

![image-20210727142159303](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142159303.png)



**git log:**

![image-20210727142346755](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142346755.png)



**git log --pretty=online:**

![image-20210727142511657](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142511657.png)



操作实验：

![image-20210727142703038](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142703038.png)

![image-20210727142726360](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142726360.png)

![image-20210727142747438](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142747438.png)

![image-20210727142836464](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727142836464.png)



注意：回到过去之后，要想回到之前的最新版本的时候回，则需要使用指令去查看历史操作

，以得到最新的commit id。

**指令：git reflog**

![image-20210727150034355](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727150034355.png)



小结：

a.要想回到过去，必须先得到commit id(git log --pretty=online)，然后通过git reset-hard进行回退

b.要想回到未来，需要使用git reflog进行历史操作查看，得到最新的commit id；

c.在写回退指令的时候commit id可以不用写全，git自动识别，但是不能写太少，至少需要写4位字符。







## 2.远程仓库

线上仓库的操作学习以Github为例。



### 2.1远程仓库的创建

![image-20210727152428709](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727152428709.png)





### 2.2两种常规使用方式

#### 2.2.1.基于http协议



![image-20210727160434899](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727160434899.png)





a.创建空目录，名称就为

![image-20210727161054088](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727161054088.png)

b.使用clone指令克隆线上仓库到本地

**语法：git clone https://github.com/wangyaxin1998/WaterLevelMeasurement.git**

![image-20210727161625344](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727161625344.png)

![image-20210727161605532](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727161605532.png)



c.在仓库上做对应的操作（提交缓存区、提交本地仓库、提交线上仓库、拉取线上仓库）

**提交到线上仓库的指令：git push**![image-20210727162839039](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727162839039.png)



在首次往线上仓库提交内容的时候，不是任何人都可以往线上仓库提交内容，必须需要鉴权



修改 git/config 文件内容

![image-20210727163233838](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727163233838.png)

![image-20210727163329211](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727163329211.png)

![image-20210727163920198](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727163920198.png)



如果另外的人在线上更改仓库内容：

**拉取线上仓库：git pull**

**提醒：每天工作的第一件事就是先git pull拉取线上最新的版本；每天下班前要做的是git push，将本地代码提交到线上仓库**



#### 2.2.2.基于ssh协议

![image-20210727165436902](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727165436902.png)

![image-20210727165419873](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727165419873.png)



②创建公私钥对文件

![image-20210727170414536](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727170414536.png)

![image-20210727170714538](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727170714538.png)



![image-20210727165935685](C:\Users\10592\AppData\Roaming\Typora\typora-user-images\image-20210727165935685.png)

