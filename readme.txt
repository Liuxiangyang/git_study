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
8.git的优秀之处在于他管理的是修改，是在git add之后的修改
