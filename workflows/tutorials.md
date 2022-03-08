


---

## Workflows in Snippets

### Snippet: Set it up!

These two are mandatory!

```
git config --global user.name "Steven Marcel Bißantz" 
git config --global user.email bissantz@uni-landau.de
```

### Snippet: Rising & Additionals!

Those are nice to have!

```
git config --global credential.helper cache
git config --global core.abbrev 7
git config --global core.editor nvim
git config --global pull.rebase true
```

### Snippet: Without? It doesn't work!

```
git init
```

If you want to be more specific!

```
git init <path/to/dir/>
```

### Snippet: Butter, Bread, ..and Chocolate!

Butter and bread!

```
git status
git add <files>
git commit 
```
Chocolate! Note: Do you want to stage and commit *all* your patches at once?
Use the following snippet. But be aware -- this can be desirable; it might not
be! ..Like chocolate.

```
git status
git commit -a
```
A compromise!

```
git status
git commit -a
```



### Snippet: The origin of your Git-verse!

```
git remote add origin git@github.com:sbissantz/repo.git 
git remote -v
git push -u origin master
```

## Workflow 1: A-Z!

Create a repository, modify some files, do the initial commit, locate a remote
repository and push!

```
git init
M-m-m-m-modify files...
git status
git add <file> <file> <file>
git commit

git status
git add <file> <file> <file>
git commit

git remote add origin git@github.com:sbissantz/repo.git 
git remote -v
git push -u origin master
```

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

## Snippet: Working with branches

```
git branch new_feature
git switch new_feature
M-m-m-m-modify files...
git switch master 
git merge new_feature
git branch -d new feature
```
The quick-n-dirty version:

```
git switch -c new_feature
M-m-m-m-modify files...
git switch -
git merge new_feature
git branch -d new feature
```

### Snippet: A-a-a-a-alias!

You can add the `logical` alias to your `.gitconfig` using by either using `git
config --global alias.<shorty> <command>. ` or adding `logical = log --color
--graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)
%C(bold blue)<%an>%Creset' --abbrev-commit` manually -- under `[alias]`-- to
your git configuration file.



