0605Linux  （GitHub知识点）

#### 关键字查询：

xx  awesome:查该标签下的xx项目

xx tutorial: 查询xx资料，书籍文档。

xx sample:查询对应技术的代码样本。

#### github三要素

**Repository 仓库,Commit 提交 ,Branch分支。**

**仓库：**

仓库是github项目的存储基本单位。

一个仓库中可以存储一个项目，一个用户可以拥有多个仓库，

一般仓库分为public,private.

**提交：**

程序员在整个开发周期，有大量对代码资源的迭代和修改。都可以通过commit提交的方式进行记录，便于程序员回溯代码。

即使这些代码被删除，也会有记录。提交便于使用者观察整个工程的开发流程以及设计流程。

**分支：**

在仓库中可以包含多个分支，分支才是代码文件的第一存储单位。

默认的仓库主分支为master/main

不仅可以管理代码存储，还便于多人协作开发。

![image-20240630134629412](C:\Users\lGY\AppData\Roaming\Typora\typora-user-images\image-20240630134629412.png)

#### 仓库内容

code ：资源存储，代码资源，二进制，项目管理脚本，许可证等。

issues：使用时遇到的Bug或进行提交，等待反馈。

README：使用markdown语言编写，工程自述文件，开发进度，版本更新，使用介绍等。

LICENSE：许可证

GPL 2.0,3.0      Apahce 2.0 Mit 这些许可证，给使用者最大使用权限和最小的限制

###### Git软件，分布式版本控制系统

仓库管理软件，使用git管理私人代码或企业代码。

![image-20240630135419351](C:\Users\lGY\AppData\Roaming\Typora\typora-user-images\image-20240630135419351.png)

#### 设备认证

1.如何让网站的账户与设备进行绑定，后续完成代码的管理，上传下载

git init //创建本地仓库

git config --list //查看git的配置文件

git config --global user.email "邮箱"

git config --global user.name "用户名"

ssh-keygen -t rsa -C "注册邮箱"  //创建本地密文

去对应的目录查找密文文件

rsa.pub 复制密文，粘贴 settings -> SSH key and GPG ->new ssh key ->粘贴

ssh -T git @github.com //测试关联是否成功。

2.为目标仓库起别名，定位目标仓库，后续上传。

git remote add orgin "ssh地址"  //为ssh仓库地址创建别名为origin

git remote remove origin // 删除origin别名

git remote add origin "ssh地址"  //为ssh仓库地址创建别名为origin

#### 本地设备与云端仓库的交互逻辑

![image-20240630140340498](C:\Users\lGY\AppData\Roaming\Typora\typora-user-images\image-20240630140340498.png)

git add code.c->git缓冲区   ->git commit  -m "提交说明" 生成提交记录

git push origin master  //将本地仓库的内容推到云端。

git status //查看状态

git rm code.c //删除本地文件及仓库中的文件

git restore code.c //复位误删除的文件

#### 代码更新的依赖关系被破坏

本地内容要比云端晚，完成更新替换，但是如果直接修改云端内容，导致本地内容无法再次提交。

先拉取git pull 云端内容与本地内容合并或操作，然后再次推即可。

git pull -- rebase origin master

git rebase --abort //忽略新版，此时还不能上传

git rebase --skip  //需忽略旧版，更新本地后可以上传。

git rebase --continue //版本合并，解决冲突后可以直接上传。

#### 下载开源代码

git clone "https仓库地址"  //下载开源项目code资源。

#### 分支Branch

关于分支的相关命令，创建分支，选择分支，合并分支等等。

#### Markdown语言

Markdown,文本修饰语言，用特殊符号修饰正文效果。

#### 标题修饰符

修饰符与正文之间要有空格

#### 正文内容

换行使用</br/>标签

段落缩进(行首加两个空格，即是分段)，也可以换行

\转义字符。

#### 字体效果

这是测试文本，斜体         *

这是测试文本，粗体        **

这是测试文本， 粗斜体   ***

这是测试文本   ~~

![image-20240630152944095](C:\Users\lGY\AppData\Roaming\Typora\typora-user-images\image-20240630152944095.png)


Markdown,文本修饰语言，用特殊符号修饰正文效果<br>

##标题修饰符\*
#  一级标题
## 二级标题
### 三级标题

##正文内容
  输入正文内容，但是如果需要换行，用\<br\>标签

##修饰正文
     *这是测试文本*  斜体

     **这是测试文本** 粗体

     ***这是测试文本*** 粗斜体

     ~~这是测试文本~~ 删除线
## 分割线
用\-\-\-表示分割线

##引用效果\>表示
> 一级引用
>> 二级引用
>>> 三级引用

##列表修饰符
###无序列表 \*
* 你好呀 (一级)
  * 测试二级
  * 测试三级
###有序列表
1. 计算机科学
   1. 分布式架构
   2. 云计算
###混合列表
1. 测试一级
   * 测试二级
   2. 测试三级
###表格
  名称|技能|排行
  --|:--|:--:
  蜘蛛侠|蜘蛛丝|live
  2024|2023|2022

### 代码片段
``` C
      #include<stdio.h>
      int main(void)
      {
          printf("hello world!");
	  return 0;
      }
``` 
``` cpp
    #include<iostream>
```
###超链接技术
[Github](https://www.github.com"点击访问")

###插入图片
![图片](C://Users//lGY//Pictures//Camera Roll//1.JPG"图片")


