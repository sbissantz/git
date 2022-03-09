
### Snippet: Modification D-day!

Drop all your local changes and commits, fetch the latest history from the
server and point your local master branch at it.

```
git fetch origin 
git reset --hard origin/master
```

### Snippet 2: Totally up-to-date

Get totally up to date ahead and behind numbers

```
git fetch --all 
git branch -vv
```

### Snippet: Rename branches -- locally & remotely 

Rename the master branch to main. Do this on remote, too (i.e. set main as new
upstream branch). Therefore we rename the branch an define the new upstream branch
(`origin/master`) explicitly. So we highlight fact that (`main`) is our new
tracking branch. After that we can rely upon `git push` to bring our patches
home (`origin`)
safely.

```
git branch --move master main
git push --set-upstream origin main
git push origin --delete master
```

### Snippet: A-a-a-a-alias!

You can add the `logical` alias to your `.gitconfig` using by either using `git
config --global alias.<shorty> <command>. ` or adding `logical = log --color
--graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)
%C(bold blue)<%an>%Creset' --abbrev-commit` manually -- under `[alias]`-- to
your git configuration file.



