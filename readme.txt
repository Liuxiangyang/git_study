1.如何在本地创建版本库？
在某个目录下面使用git init 命令即可创建git版本库

2.如何创建文件？
在目标目录下创建版本库后，在用notepad++ filename即可创建文件，如果不是在版本库目录下面则无法查找到此文件

3.如何提交创建的文件
git add filename 告诉git将文件添加到仓库缓存区
git commit -m “注释” 告诉git将缓存区的内容提交到版本区域

4.如何查看仓库是否发生改变
git status

5.如何查看具体改变了什么
git diff filename
该命令只能查看未添加到暂存区的文件
如果添加到暂存区中，那么git将会让暂存区的修改和工作区的修改进行比较
所以可以指定，当前文件和版本库的文件进行比较
git diff HEAD
所以他们比较的是修改么？

6.如何查看历史版本
git log查看历史版本
头部数字采用sha1加密
可以用HEAD^返回上一个版本
git reset --hard number/"HEAD^"

7.当回退到过去版本的时候，回不去了怎么办？
使用git relog可以查看过去的命令从而找到之前的版本

8.git的优秀之处在于他管理的是修改，仅指是在git add之后的修改

9.如何撤销工作区的修改,如何撤销暂存区的修改？
git checkout -- readme.txt 丢弃这个工作区的修改，让其返回最新版本
如果已经添加到暂存区的话需要使用 git reset HEAD file

10.删除文件，一个删除版本区的文件，一个删除工作区的文件？
工作区用rm移除文件即可
版本区需要使用git rm

11.如何添加远程库，也就是将本地版本库放到github进行备份？
首先创建ssh密匙
ssh-keygen -t rsa -C "youremail@example.com"
然后将ssh的公匙的内容放到github服务器上

添加远程库，需要在github上面创建一个仓库
之后将本地仓库与远程仓库进行关联
git add remote origin git@github.com:Liuxiangyang/git_study.git
git push -u origin master
如果不小心关联错了可以使用git remote remove origin

当推送文件出现错误提示版本落后的时候，是因为远程仓库初始化多出了几个文件
可以通过先git pull --rebase origin master(合并内容)
之后再进行推送 git push -u origin master


12.如何从远程库中克隆？
需要知道地址才能进行克隆
git clone git@github.com:Liuxiangyang/gitskills.git

13.如何创建和合并分支？
git branch name创建分支
git checkout -b dev创建并切换分支
切换分支 git checkout 分支名称
如何查看当前在哪个分支呢？
git branch
创建的新分支实际上相当于对原来状态的克隆

14.如何删除分支
git branch -d dev

15.如何合并冲突
a.使用git checkout切换到分支主线进行修改
b.提交之后切换回要合并主线，一般是master
c.之后git merge nameofbranch

16.如何管理冲突
a.首先创建并切换到新的分支
b.修改文件之后提交版本
c.返回原有分支，在同一地区进行不同的修改
d.然后提交，之后将两者进行合并
e.当冲突的时候直接进入文件进行所需要的修改，最后提交

17.分支管理策略
除了快速合并还有其他方案来进行合并么？具体如何做?
当然这只是针对，未发生冲突的快速合并，发生冲突自然另当别论

a.答案是有，禁用快速合并模式即可，但是合并的分支会有一个新的commit，可以看出来这部分是被修改过的
b.在分支同一地区修改后，git merge --no-ff -m "merge with no-ff" dev

18.分支管理原则
1.master分支保持稳定，创建一个副分支，所有修改都在副分支上面进行
2.这样做的话就会产生，不同人提交不同的分支，会有个先后的问题，有可能要先将分支拉取才可以，我将在19小结中进行使用分享问题

19.it's a test