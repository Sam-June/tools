[TOC]

https://blog.csdn.net/zs1276001750/article/details/154352175

# SVN基本操作

## 1、SVN客户端安装

### 1.1 下载SVN客户端
下载地址：https://tortoisesvn.net
TortoiseSVN程序版本下载最新的即可。
![](https://i-blog.csdnimg.cn/blog_migrate/a3414483d619c55e69f754d3bf45fafc.png)
网页里有中文语言包补丁的下载链接，可一起下载下来（中文补丁包名称以“zh_CN”结尾）：
![](https://www.runoob.com/wp-content/uploads/2018/07/5D776921-B740-484C-B753-75AF57BEE5D5.png)

### 1.2 安装SVN客户端
运行下载的TortoiseSVN安装程序，选择好安装目录后，一路“Next”：
![](https://www.runoob.com/wp-content/uploads/2018/07/install01.gif)
运行下载的TortoiseSVN中文语言包：
![](https://www.runoob.com/wp-content/uploads/2018/07/install02.gif)
安装成功后，在任一目录下，鼠标右键单击，可出现SVN菜单：
![](https://i-blog.csdnimg.cn/blog_migrate/b24e67e48d89770c377d24f74f8a8691.png)

### 1.3 设置SVN客户端默认语言
TortoiseSVN安装完后默认的界面是英文，可以通过设置修改成已安装语言：
![](https://www.runoob.com/wp-content/uploads/2018/07/changeLANG.gif)

## 2、SVN客户端的使用

### 2.1 检出SVN Repository
检出SVN Repository的过程相当于在本地PC端创建一个工作目录与远程SVN仓库形成映射。
今后在本地工作目录中做出的任何修改(如新增文件/目录、修改文件/目录、删除文件/目录)，可以通过commit命令向远程SVN仓库进行同步，也可在本地工作目录通过update命令将远程SVN仓库中的最新文件更新到本地。
**建立本地工作目录**
所谓的本地工作目录就是存放工作文件的地方，平常都是此目录下面工作，等到自己的工作做到一定的阶段，可将此目录下的文件提交到远程SVN repository中。
例如，在E盘创建文件夹Downloads作为本地SVN工作目录的根目录：
```
E:\Downloads
```
**配置检出库地址**
进入创建的Downloads目录，在空白处按下右键后，选择`SVN检出`。
![](https://i-blog.csdnimg.cn/blog_migrate/3c42b7c17fa16893994abff0e4c99f61.png)
在弹出框中，需要填写远程SVN Repository(版本库)URL的地址和检出至目录的地址：
![](https://i-blog.csdnimg.cn/blog_migrate/32490c3ebd8a7a11e1d223a5143afbad.png)
==版本库URL(仓库地址)：具体的地址可咨询部门负责人==
==检出至目录：填入本地工作目录的地址==
**接受证书**
正常情况下，SVN会提示证书认真失败，选择永久接受该证书即可：
![](https://i-blog.csdnimg.cn/blog_migrate/11c96c9d95d05261078ee3b3eada7f4c.png)
**输入用户名/密码**
SVN Repository的检出需要输入用户名和密码：
![](https://i-blog.csdnimg.cn/blog_migrate/f041e7ec09df716599c8d4dddc66a98f.png)
==用户和密码的分配，可咨询部门负责人==
**成功检出至本地**
可以看到类似于如下的输出信息：
![](https://i-blog.csdnimg.cn/blog_migrate/ac2091803b65a37612d377c990b37efb.png)
本地工作目录下面多了些文件/目录：
![](https://i-blog.csdnimg.cn/blog_migrate/5d0d4dc33878e08890ee189532abcc8c.png)

### 2.2 添加文件
在rep1文件夹下新建1.txt并保存：
![](https://i-blog.csdnimg.cn/blog_migrate/48e57f88be96689b2c9846621326985b.png)
鼠标单击右键，选择`增加`，将文件加入版本管理：
![](https://i-blog.csdnimg.cn/blog_migrate/133d308e4c45404d806d76b76a5058c9.png)
![](https://i-blog.csdnimg.cn/blog_migrate/d1c97a68484127c080b0ffffb24b87cd.png)
![](https://i-blog.csdnimg.cn/blog_migrate/cb58cdafe7e9a9c200fe71c07f492634.png)

增加成功后，文件上面多了一个“+”号：
![](https://i-blog.csdnimg.cn/blog_migrate/51415442c0b86170efac1b8fd954ce98.png)
此时，并未真正的将文件提交到远程SVN Repository中。仅仅是告知SVN准备要在Repository 中放入这些文件。
鼠标单击右键，选择`提交`，并写上备注：
![](https://i-blog.csdnimg.cn/blog_migrate/6024add8afe92861e6da25f6ff3f8d6b.png)
![](https://i-blog.csdnimg.cn/blog_migrate/fc7f9e2ab78cd1b8eb25347a2b47aa19.png)
![](https://i-blog.csdnimg.cn/blog_migrate/99e4f6d5a64efa7eae8624faf274d5f9.png)
提交成功后，文件上多了一个“✓”号：
![](https://i-blog.csdnimg.cn/blog_migrate/c76df33f58db89ad9e7142b009cfcde6.png)
此时，本地工作目录下的文件被提交至远程SVN仓库，团队其他成员可以通过SVN更新将文件更新至本地。

### 2.3 SVN更新
在团队其他成员PC上，更新SVN工作目录，鼠标单击右键，选择`SVN更新`：
![](https://i-blog.csdnimg.cn/blog_migrate/4e14c8c4e6f09644962f7d9dc84b5356.png)
可以看到刚刚提交至远程SVN仓库的文件：
![](https://i-blog.csdnimg.cn/blog_migrate/2959f1523c50f8f86df3d79440147a16.png)

### 2.4 查看日志
鼠标单击右键，选择`TortoiseSVN` -> `显示日志`：
![](https://i-blog.csdnimg.cn/blog_migrate/07cf4b62a7953c1dc56205c83b119cbe.png)
可以看到新增的日志：
![](https://i-blog.csdnimg.cn/blog_migrate/7419e7a097e435d272427574625d53b0.png)
==建议：每次提交文件时，都写上本次文件变动的备注信息，方便团队其他成员通过日志了解文档变更原因==

### 2.3 修改文件
修改文件并保存，文件图标变为红色感叹号：
![](https://i-blog.csdnimg.cn/blog_migrate/5e0ac39413b3ea6c7cc1c4c9a1186b88.png)
鼠标单击右键，选择`提交`，提交修改：
![](https://i-blog.csdnimg.cn/blog_migrate/5e418c4c383e59f6d0732dbf9bdbbe07.png)
填写备注：
![](https://i-blog.csdnimg.cn/blog_migrate/7fc38803c40678434f41224a0caab461.png)
提交完成：
![](https://i-blog.csdnimg.cn/blog_migrate/93e88e3b65fa3aa91a912f0367c98acb.png)
鼠标单击右键，选择`TortoiseSVN` -> `显示日志`，查看日志：
![](https://i-blog.csdnimg.cn/blog_migrate/2610833ff7bb592b5fc69df17a005f25.png)
双击日志，可以显示出和上个版本的区别：
![](https://i-blog.csdnimg.cn/blog_migrate/b3aa47e3c00b80915af72659ce67ffb2.png)
![](https://i-blog.csdnimg.cn/blog_migrate/91a70642a562ed1f8dc003657cca8fb2.png)

**由于版本控制系统都是由多人协同工作。所以，同样的文件可能还有其他人会去进行编辑。为了确保本地工作目录中的文件与远程SVN Repository中的文件是同步的。建议在本地编辑前都先进行Update更新的动作。**


## 3、参考资料
1. SVN入门教程，超简单，30分钟学会！——https://blog.csdn.net/qq_45527691/article/details/122302359
2. SVN客户端TortoiseSVN基本使用方法步骤-初人指南——https://blog.csdn.net/u014779536/article/details/115877335

