# Git Common Scenario

## 本地落户于远程仓库

```linux
! [rejected]        main -> main (non-fast-forward)
Updates were rejected because the tip of your current branch is behind
```

当你`git pull` 尝试拉取远端新内容, 而远端 `main` 上已经有新的提交，而你本地 `main` 没有这些提交时, 先拉取再推送.

`git pull origin main --rebase`

`git push origin main`

```linux
# 假设远端有提交
A - B - C   (origin/main)

# 我本地也有提交
A - B - D   (main)

# git pull --rebase 后再推送可以保持线性
A - B - C - D   (main)
```

---

## .git 突然消失

```linux
fatal: 'react/prjWithOrganized/.git' not recognized as a git repository
```

进入相关目录 `dir -force`

- 如果没有 `.git`

```linux
git init
git remote add origin <你的远程仓库地址>
```

- 如果有 `.git` 那可能是坏了

```linux
rmdir -force .git -recurse
git init
git remote add origin <你的远程仓库地址>
```

## 碰到某个文件怎么都加不进 git 版本控制里

```linux
  (commit or discard the untracked or modified content in submodules)
        modified:   react/prjWithOrganized (untracked content)
```

是因为该文件路径是一个子模块.

把它并入外层仓库（不当子模块）

```linux
# 1. cd 到 根目录并移除子模块配置
git rm -r --cached react/prjWithOrganized

# 2. 删除 .gitmodules
rm .gitmodules

# 3. 打开 .git/config , 有下面这段旧删掉
[submodule "react/prjWithOrganized"]
    path = react/prjWithOrganized
    url = ...
    
# 4. 提交清理
git commit -m "remove submodule prjWithOrganized"
git push origin main

# 5. 重新加入本地文件夹
git add react/prjWithOrganized
git commit -m "add prjWithOrganized as normal folder"
git push origin main
```

## 代码改错了 一键回到当前 commit 的最初状态

`git reset --hard`

## 改上一次 commit 信息

```linux
git commit --amend
git push --force
```

## 在分支 fix bug 最后只合并一条 commit 到 main

```linux
git checkout main
git merge --squash test-branch
```

## 多行 commit

`git commit` (不加 `-m`)

## 在 dev 分支以最新状态继续开发

```linux
# 进入 dev 分支
git checkout dev
# 拉取远程 main 再合并 origin/main
git pull origin main
# 强制推送到远端 dev 分支
git push -f origin dev
```

