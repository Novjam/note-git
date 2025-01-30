git 三个区域，分别是工作区->暂存区->仓库

查看三区状态：git status

工作区->暂存区：git add .

暂存取->仓库：git commit -m '描述'

回滚commit：git reset --hard commit的ID

查看commit日志：
1）git log --pretty=oneline --all --graph --abbrev-commit
可创建.bashrc文件放于用户目录下，添加项alias git-log='git log --pretty=oneline --all --graph --abbrev-commit'，简化输入

2）git reflog 可查看被回滚的commit记录

分支
查看当前所有分支：git branch
创建xxx分支：git branch xxx
切换到xxx分支：git checkout xxx
创建并切换到xxx分支：git checkout -b xxx
删除xxx分支：git branch -d xxx
强制删除xxx分支（xxx分支可能有未合并的内容）：git branch -D xxx

