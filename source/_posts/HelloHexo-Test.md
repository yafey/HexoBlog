---
title: HelloHexo Test
date: 2017-05-28 01:21:39
tags: test
---

测试

# 1



# Git submodules: Specify a branch/tag
https://stackoverflow.com/questions/1777854/git-submodules-specify-a-branch-tag
umläute refines dtmland's command with a simplified version [in the comments](https://stackoverflow.com/questions/1777854/git-submodules-specify-a-branch-tag/18799234#comment54105039_18799234):
```
git submodule foreach -q --recursive 'git checkout $(git config -f $toplevel/.gitmodules submodule.$name.branch || echo master)'
```
multiple lines:
```
git submodule foreach -q --recursive \
  'git checkout \
  $(git config -f $toplevel/.gitmodules submodule.$name.branch || echo master)'
```


## GETTING GIT SUBMODULE TO TRACK A BRANCH (add submodule 的步骤)
https://www.activestate.com/blog/2014/05/getting-git-submodule-track-branch
  - 删除 submodule : `git rm --cached <mysubmodule>`
  - add submodule : `git submodule add --force -b BUAT <git url> <submodule path>`
  - Add a submodule which can't be removed from the index
  https://stackoverflow.com/questions/12218420/add-a-submodule-which-cant-be-removed-from-the-index
  >  If the output adding a new submodule is:
  ```
  	#'FolderName' already exists in the index
  	# Tip the next commands
  git ls-files --stage
  	# The output will be something similar to:
  160000 d023657a21c1bf05d0eeaac6218eb5cca8520d16  0  FolderName
  	# Then, to remove the folder index tip:
  git rm -r --cached FolderName
  	#Try again add the submodule
  ```
