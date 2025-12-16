https://blog.csdn.net/m0_68657832/article/details/137120385?ops_request_misc=%257B%2522request%255Fid%2522%253A%25226603416e6bbe90458cdaf4c5da05cf9c%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fblog.%2522%257D&request_id=6603416e6bbe90458cdaf4c5da05cf9c&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~first_rank_ecpm_v1~rank_v31_ecpm-1-137120385-null-null.nonecase&utm_term=git&spm=1018.2226.3001.4450
# 一、git的定义
git是一款分布式版本控制器软件。每台电脑都是一个对应的版本库，无需联网即可进行版本控制。多人协作只需要各自的修改推送给对方，就能互相看到对方的修改。

相对应的，SVN和CVS就是集中式版本控制器软件。需要联网才能获得最新版本，修改后需要提交到服务器。显然，git更加先进。

# 二、git的全貌图
![git的全貌图](image.png)
从这里我们可以看到，一共有四个区域，分别是：
1. `工作区`（Working Directory）
2. `暂存区`（Stage/Index）
3. `本地仓库`（Local Repository）
4. `远程仓库`（Remote Repository）
---

把这几个区域的关系转换搞清楚，那基本就可以万事大吉了！接下里的工作也基本是围绕这些进行的。

# 三、git的基本操作
## (一)安装与登录
安装就很简单，下载就好了，下载后，可以使用git bash终端进行操作。

安装后，`登录`是重头戏，需要配置`用户名`和`邮箱`。
我们知道，平时我们玩游戏时，为了区分不同玩家都需要进行登录。那么，显然在git中，我们也需要进行登录,用来区分唯一的用户。

### 1.登录的命令如下：

```
git config --global user.name "EthanYankang"
git config --global user.email "2126483838@qq.com"
```
如下:
![设置信息](image-2.png)
### 2.查看配置信息
```
git config --global user.name
git config --global user.email
```
如下：
 
![查看git信息](image-3.png)

## (二)创建本地仓库
### 1.创建本地仓库
好了，前面的登录操作完成后，我们就可以创建本地仓库，正式进行操作了！
命令如下：
```
git init
```
![创建的就是第三个区域，本地仓库](image-4.png)

![不同人员开发的过程](image-6.png)
### 2.文件的状态
Git工作目录下对于文件的修改(增加、删除、更新)会存在几个状态，这些修改的状态会随着我们执行Git的命令而发生变化。

![本图是git文件的状态在工作区、暂存区、本地仓库间的变化的命令图](image-5.png)

```
git add <file> //将文件从工作区添加到暂存区
git commit -m "提交信息" //将暂存区的文件提交到本地仓库
git status //查看文件的状态
```
#### 1.测试
刚刚初始化后，查看文件状态
```
git status
```
![查看文件状态](image-7.png)
可以看到，这些文件都没有被跟踪，即仍然在工作区，还没有到暂存区。
下面使用git add命令将这些文件添加到暂存区
```
git add .
```
![将文件添加到暂存区](image-8.png)
可以看到，这些文件都被添加到了暂存区。
