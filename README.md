# Git Common Scenario

## 本地落户于远程仓库

```linux
! [rejected]        main -> main (non-fast-forward)
Updates were rejected because the tip of your current branch is behind
```

当你`git pull` 尝试拉取远端新内容, 而远端 `main` 上已经有新的提交，而你本地 `main` 没有这些提交时, 先拉取再推送.

`git pull origin main --rebase`

`git push origin main`

