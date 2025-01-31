配置用户名和邮箱
git config --global user.name xxx
git config --global user.email xxx
查看用户名和邮箱
git config --global user.name
git config --global user.email

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

合并分支
先用git checkout target分支 切换到target分支，使用git merge ource分支 将source分支合并到target分支
若无冲突，则直接合并成功，否则
在target分支找到冲突文件，解决冲突，然后git add .命令加上git commit命令完成分支的合并

连接远程仓库
生成SSH公钥
ssh-keygen -t rsa一路回车
获取公钥（公钥用于远程仓库的配置）
cat ~/.ssh/id_rsa.pub
验证是否配置成功
ssh -T git@gitee.com
从远程仓库获取SSH地址
git remote add origin 远程仓库的SSH地址
查看远程仓库
git remote
或git remote -v
推：git push [-f] [--set-upstream] [远端名称 [本地分支][:远端分支]]
[-f]表示强制覆盖（威胁操作）
[--set-upstream]建立本地分支到远程分支的关联关系
查看本地分支到远程分支的关联关系 git branch -vv
git push origin master:master
