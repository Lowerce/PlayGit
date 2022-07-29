## Notes
#### Git入门教程 https://learngitbranching.js.org/
#### 命令
  
- `git branch -f <branch_name> <move-to-hash>`
- `git reset <move-to-hash>`
- `git merge <move-to-hash>`
  *移动分支到某个引用*
  
- `git rebase <base_hash>`
- `git rebase -i <base_hash>`
  *变基*

- `git cherry-pick <hash1> <hash2> ...`
  *提取已有hash组成现有分支*

- `git revert <hash>`
  *在hash后创建hash^的副本(回退)*

- `git pull` == fetch + merge
- `git pull --rebase` == fetch + rebase
  *在远程仓库有更新时便于push*

- `git push <remote_name> <branch_name>` 最后一个参数同时说明了来源和去向
- `git push <remote_name> <source_branch>:<destination_branch>` 来源和去向不同，远程分支中没有去向分支时则自动创建
  *带参数的push，带参数的fetch、pull与之类似，只是来源和去向相反*


- `git merge --no-ff <hash>`
  *禁用快速移动合并工作，强制在hash后创建新的commit而不是仅仅移动指针(快速移动)*

- `git checkout -b <new_branch_name> <remote_name/remote_branch_name>`
- `git branch -u <remote_name/remote_branch_name>`
  *本地分支与远程分支的绑定*


#### 学习笔记

- 实际使用和练习之间存在着一些不同，在练习中快照和分支的关系十分清晰，并且显示了那些在`git log`中不会显示的、已经隐藏的快照(使用`git reflog`查看所有历史操作及hash)
- 所有的操作尽量都在**分支**上进行，而不是对分离的HEAD执行操作，二者在一些情况下的行为是不一样的
- 很重要的一点是弄清`merge`和`rebase`的适用场景，提供一些供参考的标准:
  - 永远不要在**公共**分支上使用`rebase`，`rebase`操作要十分谨慎，会修改提交树的历史，但可以使提交树保持线性

- 使用`rebase -i`后，覆盖到的`commit`按从早到晚的顺序自上而下排列，所以要优先修改选定靠下的`commit`的状态
- 所谓的**PR**并不是一种独立的操作，在主分支*锁定*的情况下，需要按要求`新建分支`然后`push`
- `git clone`会自动将本地分支和远程分支绑定
- `push`和`fetch`参数中的*source*可以为空值，push则为删除指定分支，fetch则为创建指定分支
  