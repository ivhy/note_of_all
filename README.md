### 本地的项目想丢到GitHub上

- 连接远程仓库，把本地仓库与远程仓库连接起来，运行命令：`git remote add online git@github.com:yourGitHubId/testRepo.git`，这里add后面的online是随便取的，官方习惯用origin，我这里用online，然后运行`gir remote -v`查看当前连接的远程仓库信息。
- 本地文件首次提交到远程仓库，运行命令`git push -u online master`，完成后就可以在远程仓库中看到这些文件了，之后的提交不需要加`-u`。

### GitHub有仓库，本地也有项目，想合并到一块

- 创建本地仓库，并提交当前所有修改到本地仓库
- 连接远程仓库。运行命令：`git remote add origin git@github.com:yourGitHubId/testRepo.git`，可以看到远程仓库信息。
- 从拉取远程仓库文件，跟上一种情况不一样，前面是直接推送到远程空白仓库，现在是先从远程仓库拉取文件，正常拉取的命令是`git pull origin master`，git报警告`fatal: refusing to merge unrelated histories`，意思是“拒绝合并不相关的历史”。因此要强行合并，使用命令`git pull origin master --allow-unrelated-histories`，拉取搞定。