Git 常用操作命令

安装
1.安装Git，使用bash命令操作。 Git下载

2.设置Git的user name和 email：

git config --global user.name "xxx"
git config --global user.email "xxx@xxx.com"
Image text

3.生成SSH密钥： 密钥在生成提示的路径中查看，[id_rsa]为私人密钥，[id_rsa.pub]为公钥

ssh-keygen -t rsa -C "xxx@xxx.com"
Image text

4.在Github个人中心setting上添加ssh密钥，这要添加的是"id_rsa.pub"里面的公钥。

Image text




基础使用
# 克隆远程仓库项目
git clone xxx.git

# 更新代码
git pull

# 查看状态
git status

# 添加文件 [所有文件用 .]
git add fileName

# 提交文件到本地仓库
git commit -m '这是注释'

# 提交文件到远程仓库
git push origin master



创建版本库
# 克隆远程仓库项目
git clone xxx.git

# 始化本地仓库初
git init

# 关联远程仓库（这里作用是本地创建的文件夹与远程的关联）
git remote add origin xxx.git



修改和提交
# 查看状态
git status

# 查看变更内容
git diff

# 添加所有发动过的文件
git add .

# 添加指定文件
git add <file>

# 文件改名
git mv <old> <new>

# 删除文件
git rm <file>

# 删除文件夹
git rm -r <file>

# 停止跟踪文件但不删除
git rm --cached <file>

# 提交文件到本地仓库
git commit -m "这是注释"

# 提交所有修改到本地仓库
git commit -a -m "这是注释"

# 提交文件到远程仓库
git push origin master



查看提交历史
# 查看提交历史
git log

# 查看指定文件的提交历史
git log -p <file>

# 以列表的方式查看指定文件的提交历史
git blame <file>



撤消
# 撤消工作目录中所有未提交文件的修改内容
git reset --hard HEAD

# 撤消指定未提交文件的修改内容
git checkout HEAD <file>

# 撤消指定的提交
git revert <commit>



分支与标签
# 显示所有本地分支
git branch

# 切换到指定分支或标签
git checkout <branch/tag>

# 创建新分支
git branch <new-branch>

# 删除本地分支
git branch -d <branch>

# 列出本地分支
git tag

# 基于最新提交创建标签
git tag <tagname>

# 删除标签
git tag -d <tagname>



合并与变基
# 合并指定分支到当前分支
git merge <branch>

# 变基指定分支到当前分支
git rebase <branch>



远程操作
# 查看远程版本库信息
git remote -v

# 查看指定远程版本库信息
git remote show <remote>

# 添加远程版本库
git remote add <remote> <url>

#从远程库获取代码
git fetch <remote>

# 下载代码及民以快速合并
git pull <remote> <branch>

# 上传代码及快速合并
git push <remote> <branch>

# 删除远程分支或标签
git push <remote> :<branch/tag-name>

# 上所有标签
git push --tags



常见问题
# 1.解决 Git pull/push 每次都需要输入密码问题， 运行后第一次需要输入账号密码，后面就不需要了.
git config --global credential.helper store

# 2.解决关于Git无法提交 index.lock File exists的问题
在目录中隐藏的.git 目录下找到index.lock 删除即可



小结
以上常用命令都是由网络收集整理而来，如果对您有帮助欢迎给个Star ~ Y(^_^)Y