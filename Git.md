**1.新建git本地文件夹**

`mkdir gitpjt`

**2.初始化仓库**

从本地新建并产生初始化文件
`git init`

或者从远程克隆版本库
`git clone rep_url`

**3.新建介绍文件**

`vim readme.md`

**4.本地->缓冲区**

只添加指定文件
`git add readme.md` 

添加当前文件夹内所有文件
`git add .`

**5.缓冲区->仓库**

`git commit -m "add readme.md`

**6.更改本地文件内容，版本比较中如果缓冲区有该文件则将缓冲区与本地文件比较，如果没有则仓库文件与本地文件比较**

`git diff readme.md`

**7.查看当前状态**

`git status`

**8.查看日志**

当前版本之前的md5日志：
`git log`

简单日志：
`git log --pretty=oneline`

所有版本信息的md5日志：
`git reflog`

查看指定文件的提交日志
`git log -p file_name`

以列表形式查看指定文件的日志
`git blame file_name`

**9.缓冲区版本撤销并覆盖本地版本**

`git checkout -- readme.md`

**10.仓库以前版本找回并覆盖本地版本**

回到前1个版本
`git reset --hard HEAD^` 

回到前3个版本
`git reset --hard HEAD^^^` 

xxx表示每个版本对应的md5前7位数，可以在log和reflog中查看，可以回到任何版本
`git reset --hard xxxxxxx`  

**10.删除仓库中的文件**

删除仓库的文件，但保留本地的该文件
`git rm --cached readme.md` 

删除仓库的文件，同时强制删除本地的该文件
`git rm -f readme.md` 

注意：删除后的文件在git reflog中无法找到md5，所以无法找回以前的版本，应该慎重并做好备份

**11.修改文件名称**

`git mv old_name new_name`

**12.修改最后一次提交**

`git commit --amend`

**13.分支branch与标签tag**

显示所有本地分支
`git branch`

切换到指定分支或标签
`git checkout <branch/tag>`

创建新的分支
`git branch <new_branch_name>`

删除本地分支
`git branch -d <branch_name>`

列出所有本地标签
`git tag`

基于最新提交创建标签
`git tag <tag_name>`

删除标签
`git tag -d <tag_name>`

14.合并与衍合

合并指定分支到当前分支
`git merge <branch_name>`

衍合指定分支到当前分支
`git rebase <branch_name>`

**15.远程操作**

查看远程版本库信息
`git remote -v`

查看指定远程版本库信息
`git remote show <remote>`

添加远程版本库
`git remote add <remote> <url>`

从远程库获取代码
`git fetch <remote>`

下载代码及快速合并
`git pull <remote> <branch>`

上传代码及快速合并
`git push <remote> <branch>`

删除远程分支或标签
`git push <remote> :<branch/tag_name>`

上传所有标签
`git push --tags`
