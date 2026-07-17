# git笔记
---

## 常用命令：
|命令|解释|
|---|---|
`git add file`				|					添加文件到暂存区
`git add .`					|						添加工作区所有文件到暂存区
`git commit -m "tip"`|									将暂存区所有文件上传到仓库，备注tip
`git log`	|										查看提交到仓库的时间戳和地址
`git status`	|										查看工作区，暂存区，仓库的区别
`git diff`		|									比较工作区与暂存区的区别
`git diff --staged`		|							比较暂存区和仓库的区别
`git status`|红色字提示工作区和暂存区存在差异，绿色字提示暂存区和仓库存在差异
`git reset --hard id`|改仓库，将工作区，暂存区回退到对应id的仓库版本（会删除所有没有提交的修改，所以慎重使用）
`git reset --hard HEAD^`|仓库回退到上一个版本
`git checkout -- file`|若暂存区不为空，工作区被暂存区覆盖；若为空，被仓库覆盖。可以实现类似于“一键还原”的功能
`git reset HEAD file`|暂存区被仓库最新版本覆盖，工作区不变
`rm file`|删除工作区文件
`git rm file`|删除工作区和暂存区文件
`git log --oneline`		|							只用一行显示日志
`git remote add origin git@github.com:用户名/仓库名.git`	|	将本地与远程库（github中创建的仓库）关联
`git remote add origin https://github.com/用户名/仓库名.git`	|同上
`git remote remove origin`			|				删掉旧的关联
`git remote -v`				|						检查关联
`git push -u origin master`			|					第一次推送
`git push`					|						以后上传
`git clone git@github.com:用户名/仓库名.git`		|		从远程克隆下来
`git clone https://github.com/用户名/仓库名.git`	|			同上
`git checkout -b dev` 或 **`git switch -c dev`**    |								创建并切换到dev分支
`git checkout dev` 或 **`git switch dev`**	|									切换到dev分支
`git branch -d dev`	|									删除dev分支
`git merge dev`	|										将dev分支合并到默认(master)分支
`git branch`	|										查看所有分支(带*号的就是当前分支)
---
## 常用快捷键：
|快捷键|功能|
|---|---|
`CTRL+C`	|										停止工作区卡住
`CTRL+INSERT`										|复制
`SHIFT+INSERT`										|粘贴
---
## 另外知识
1. **远程仓库的默认分支是 main，而本地仓库的默认分支是 master。**

   -   方案 A：直接改掉默认分支的名字
 GitHub 的仓库页面， More - Settings - General - Default branch，有一个画笔的图标，点击，把它从 main 名字改成 master。
   -   方案 B：在本地把 master 和 main 对齐
如果不想改 GitHub 的设置，在本地终端按顺序敲这三行命令把它们合并：

        ```bash
        git pull origin main
        git checkout main
        git merge master
        ```    
   -   方案 C：如果不想更改
GitHub 的仓库页面， More - Settings - General - Default branch，有一个双箭头图标，点击把它从 main 改成 master。(**好处在于`git clone`的时候，默认clone的是 master 分支，而不是 main 分支。**)

2. 使用`git log`的时候，可能会显示非常长的信息，最后是一个冒号`:`，这时候你会发现无法输入命令。

   -   解决办法：按下`q`键退出