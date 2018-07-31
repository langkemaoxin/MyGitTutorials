# MyGitTutorials
这是我的Git学习项目


# 删除本地的分支

### 1.使用场景：开了过多的项目，一定时间需要清除本地分支
### 执行命令： 
> git branch | grep -v -E 'master|develop' | xargs git branch -d -f

+ git branch 列出本地所有分支
+ grep -v -E 'master|develop' 搜索排除 master,develop的所有分支
+ xargs 把之前所有的管道信息作为参数 传给一下一个命令
+ git branch -d -f 强制删除分支  -d:删除 -f:强制

### 2.使用场景：删除某一个目录，满足通配符的
### 执行命令： 
> git branch | grep 'zhanshan/*' | xargs git branch -d -f


