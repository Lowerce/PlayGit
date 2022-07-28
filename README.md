## Notes
#### Git入门教程 https://learngitbranching.js.org/
#### 命令
  
- `git branch -f <branch_name> <move-to-hash>`
- `git reset <move-to-hash>`
  *移动分支到某个引用*
  
- `git rebase <base_hash>`
- `git rebase -i <base_hash>`
  *变基*

- `git cherry-pick <hash1> <hash2> ...`
  *提取已有hash组成现有分支*

- `git revert <hash>`
  *在hash后创建hash^的副本(回退)*

