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
    git restore --staged README.md 将指定文件覆盖为上一次提交的文件，改动会没，工作区改为上次工作区
    
    commit后
        
        还没push
        git reset <提交号> 回退到指定版本，改动回到工作区
        git reset <提交号> 回退到指定版本，改动删除，工作区与上次提交时相同

        push后
        git revert <提交号> 交一笔反向的新提交


写gitignore：看.ignore文件