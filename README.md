# MyGitTutorials
这是我的Git学习项目


# 删除本地的分支

### 1.使用场景：开了过多的项目，一定时间需要清除本地分支 
> git branch | grep -v -E 'master|develop' | xargs git branch -d -f

* git branch 列出本地所有分支
* grep -v -E 'master|develop' 搜索排除 master,develop的所有分支
* xargs 把之前所有的管道信息作为参数 传给一下一个命令
* git branch -d -f 强制删除分支  -d:删除 -f:强制

### 2.使用场景：删除某一个目录，满足通配符的 
> git branch | grep 'zhanshan/*' | xargs git branch -d -f


# 分支管理 
 
查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

> git push origin master

将本地的master分支推送到origin主机的master分支。如果master不存在，则会被新建。

# 把暂存区的修改移除 
> git reset HEAD .

# 把工作区的修改移除
> git checkout .

# 合并Develop分支到本地开发分支如何撤销
+ 没有推送到远端之前



# 使用案例：git回滚到任意版本 [时光穿梭机]

# 案例场景：
1.多人把自己的开发分支 合并到develop_test上面
2.当前版本有问题，想远端的develop_test恢复到合并之前的版本

# 具体操作
1. 切换到 develop_test 分支
2. 查找想要回滚的那次提交 commit Id,如：83d70fe7
3. 强制回滚到指定的版本 --> git reset --hard 83d70fe7
4. 强制推送到远端 --> git push -f origin develop_test

# 具体原理：
1. Git 有个 HEAD指针指向最后一次提交的版本
2. 使用Git reset 可以改变HEAD指向的版本
3. 使用Git push -f 把改变指针的命令作用于远端 