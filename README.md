#这是一个lzq github使用教程

git --version 获取版本

git config --global user.name "xxx" 绑定此电脑提交时的账号名
git config --global user.name 查询此电脑绑定的账号名
git config --global user.email "xxx" 
git config --global user.email

git一共有三个区域：工作区 暂存区 仓库

git init 创建.git文件

git status 看git状态，输出暂存区文件

git add README.md 将文件从工作区放入暂存区
git add . 把所有文件加入暂存区

git commit -m "第一次提交：加入README" README.md 将修改存入历史，创建一个可回溯节点
git commit -m "说明" 保存所有暂存区文件
 
git log --oneline 查看提交记录 

git ls-files 看git一共追踪了哪些文件

git diff 查看工作区(需先保存到磁盘)与暂存区的代码区别
git diff --staged 查看暂存区与上一次提交代码区别
看代码异同建议在vscode中看

撤回的多种方法
    
    没有commit时
    git restore README.md 将指定文件覆盖为到上一次提交的文件
    git restore --staged README.md 将指定文件从暂存区回到工作区
    
    commit后
        
        还没push
        git reset <提交号> 回退到指定版本，改动回到工作区
        git reset --hard <提交号> 回退到指定版本，改动删除，工作区与上次提交时相同

        push后
        git revert <提交号> 交一笔反向的新提交


写gitignore：看.ignore文件

git stash 暂存所有未commit的文件，包括暂存区和工作区
git stash -u 新建和未追踪的都stash住
git stash pop 把收起的文件拿出来

git switch -c 分支名 创建新分支并切换过去
git branch 查看所有本地分支
git switch 分支名 切到指定分支
git switch main 切回主分支
git merge 分支名 合并分支到main
有冲突的话删代码后再add，commit
git branch -d 分支名 删除分支

小tips：switch之前若工作区某一文件和目标分支commit文件不一样则改动需先stash或先commit，否则git不知道保存哪个，会拒绝switch
多个分支共享工作区和暂存区，在switch的时候会跟随(若不想跟随的话可以stash)


git remote add origin 仓库地址 将本地文件与github项目关联
git remote -v 列出登记过的名字
git push -u origin main 推上去，第一次推需要-u将origin和main记住配对
git push 后续直接push就行
git pull 拉去远程改动并合并
git fetch 拉去不合并

git tag v1.0.0 打标签
git push origin --tags 将标签与此次推送绑定

git blame 文件名 看每一行都是谁改的

git reflog 防止误删

