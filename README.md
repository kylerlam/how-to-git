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

