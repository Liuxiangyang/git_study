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
