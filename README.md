# 建立两个仓库

```
#假定创建好的两个仓库地址分别为：

https://gitee.com/chenchongbiao/sync-test.git

https://github.com/chenchongbiao/sync-test.git
```

# 先从其中一个仓库检出代码

```bash
git clone https://gitee.com/cigoos/mycode.git
```

# 删除仓库origin

```bash
git remote rm origin
```

# 关联两个远程仓库

```bash
# 关联gitee
git remote add gitee https://gitee.com/chenchongbiao/sync-test.git
git push gitee master

# 关联github
git remote add github https://github.com/chenchongbiao/sync-test.git
git push github master
```

```bash
# 注意此时如果遇到下述问题
To https://github.com/chenchongbiao/sync-test.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/chenchongbiao/sync-test.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

# 此时要先执行
git pull github master --allow-unrelated-histories
```

# 删除分支

```bash
git push origin --delete dev

git branch -D dev
```

# 检出本地分支

```bash
#基于gitee/master创建本地分支gitee
git checkout -b gitee/master gitee
```

# 合并分支

```bash
git merge --squash dev --allow-unrelated-histories
```
