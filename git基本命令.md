- **markdown 当你使用Git进行版本控制时，以下是一些常用的Git命令及其说明：**
    
- `git init`：初始化一个新的Git仓库。
    
- `git clone <repository>`：克隆（下载）一个远程Git仓库到本地。
    
- `git add <file>`：将文件添加到暂存区。
    
- `git add .`：将所有修改的文件添加到暂存区。
    
- `git commit -m "<message>"`：将暂存区中的文件提交到版本库，附带提交信息。
    
- `git status`：查看工作区和暂存区的状态。
    
- `git log`：查看提交日志，显示最近的提交记录。
    
- `git log --oneline`：以简洁的形式显示提交日志。
    
- `git log --graph`：以图形化形式显示提交历史。
    
- `git branch`：列出所有分支，当前分支前面会有一个星号标记。
    
- `git branch <branch>`：创建一个新分支。
    
- `git branch -d <branch>`：删除指定的分支。
    
- `git checkout <branch>`：切换到指定分支。
    
- `git checkout -b <branch>`：创建并切换到一个新分支。
    
- `git merge <branch>`：将指定分支合并到当前分支。
    
- `git push <remote> <branch>`：将本地分支的提交推送到远程仓库。
    
- `git push -u <remote> <branch>`：将本地分支的提交推送到远程仓库，并将该分支设置为远程跟踪分支。
    
- `git pull <remote> <branch>`：从远程仓库拉取更新到本地分支。
    
- `git remote`：列出所有远程仓库。
    
- `git remote -v`：显示远程仓库的详细信息，包括URL。
    
- `git remote add <name> <url>`：添加一个远程仓库，并指定一个别名。
    
- `git remote remove <name>`：移除指定的远程仓库。
    
- `git diff`：查看工作区与暂存区之间的差异。
    
- `git diff --cached`：查看暂存区与最新提交之间的差异。
    
- `git diff <commit1> <commit2>`：查看两个提交之间的差异。
    
- `git reset <file>`：将指定文件在暂存区的修改撤销，但保留工作区的修改。
    
- `git reset --hard`：将当前分支的HEAD指针重置到指定的提交，并丢弃所有的工作区和暂存区的修改。
- `git revert <commit>`：撤销指定提交的更改，生成一个新的提交来表示撤销操作。
    
- `git stash`：将当前的工作目录暂存起来，以便切换到其他分支进行操作。
    
- `git stash list`：显示所有的工作目录暂存记录。
    
- `git stash apply`：恢复最近一次暂存的工作目录，并将其从暂存区移除。
    
- `git cherry-pick <commit>`：将指定提交应用到当前分支。