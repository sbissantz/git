# New features!

Creating new features is key to push your project forward. As part of good
practice, I recommend creating a branch, changing stuff and merging the patches
back into your master branch. In this way, you can never mess up your master
branch directly. Ah, I should note: actually we do not merge; we rebase! 
For the merginados I'll c-p and adapted version at the end.

```
git branch new_feature
git switch new_feature
M-m-m-m-modify files...
git switch master 
git rebase new_feature 
git branch -d new feature
```
The quick-n-dirty version:

```
git switch -c new_feature
M-m-m-m-modify files...
git switch -
git rebase new_feature 
git branch -d new feature
```

For the merginados:

```
git switch -c new_feature
M-m-m-m-modify files...
git switch -
git merge new_feature 
git branch -d new feature
```

