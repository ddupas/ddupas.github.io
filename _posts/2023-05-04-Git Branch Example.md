---
title: Git Branching Example
categories:
  - Git
header:
image: 
tags:
  - Git
  - Develop
---

## show remotes
```
git remote -v
```

## see if there is an update on remote
```
git remote update
```

## catch up to remote
```
git pull
```

## plan edit by creating branch and checking it out
```sh
git checkout -b <edit-name>
```

## show branches
```
git branch
```

## make commit on current branch
```
git commit -a
```

## push branch commit upstream, will provide pull request url
```
git push --set-upstream origin <edit-name>
```

## after pull request approved, we must update and pull
```
git remote update
git checkout main
git pull
```




