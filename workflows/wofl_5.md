# Rename a branches -- locally & remotely 

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
