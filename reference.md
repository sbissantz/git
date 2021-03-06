# Command reference

---

# git config

| Syntax | Description |
| ------ | ----------- |
| `git config <key>` | Show me the `<key>` configuration |
| `git config --show-origin <key>` | Show me in which file the `<key>` configuration lives | 
| `git config --list` | Show me all configurations (in all config files) |
| `git config --list --show-origin` | Show me all configurations & the files where they live |
|  |  |
| `git config --global user.name "foo bar"` | Make `foo bar` my global user's id |
| `git config --global user.email foo@bar.com` | Make `foo@bar.com` my global user's mail address |
|  |  |
| `git config --global core.editor <editor>"` | Make `<editor>` my global user's default text editor |
| `git config --global init.defaultBranch <branch>"` | Make `<branch>` my global user's default initialization branch |
| `git config --global credential.helper cache`| Make a `credential.helper` `cache` my password for a few minutes|
| `git config --global pull.rebase true`| Make rebasing my default pulling strategy |
|  |  |
| `git config --global core.abbrev 7` | Make the length of SHA-1 Hash 7|
|  |  |
| `git config --global alias.<alias> <command>"` | Set up `<alias>` for `<command>` |
|  |  |
| `git config --system` | Apply system wide changes (i.e., `/etc/gitconfig` -- affects all users & each of their repositories -- ) |
| `git config --global` | Apply user wide changes (i.e., `.gitconfig` -- affects all repositories for a single user) |
| `git config --local` | Apply repository wide changes (i.e., `.git/config`  |


Note: `system < global < local`. Which means, changes applied to a local
`.git/config` overwrites the system-wide changes in `/etc/git`.

---

# git help

| Syntax | Description |
| ------ | ----------- |
| `git help <verb>` | Help me with `<verb>` |
| `git <verb> --help` | Help me with `<verb>` |
| `man git-<verb>` | Show me `<verb>`'s man page |
| | |
| `git <verb> -h` | Show me all options for `<verb>` |

---

# git init

| Syntax | Description |
| ------ | ----------- |
| `git init` | Re-/initialize a git repo in my current directory |
| `git init <dir/>` | Re-/Initialize a git repo in `<dir/>` |
| `git init --bare <repo>.git`| Initialize a bare `<repo>.git` (i.e., a repo without a working directory; or the true nature of the "remote repo") |
| `git init --bare --shared <repo>.git`| Initialize a bare `<repo>.git` with group write permissions |

---

# git status

| Syntax | Description |
| ------ | ----------- |
| `git status` | Check the *state* of my files (i.e., un-/tracked, un/-modified, un-/staged) |
| `git status --short` | Check the *state* of my files in a short format |

---

# git add

| Syntax | Description |
| ------ | ----------- |
| `git add <untracked_file>` |  Start tracking the `<untracked_file>` |
| `git add <file_1> <file_2>` | Start tracking the *untracked* files -- `<file_1>`, `<file_2>` |
| `git add -i` |  Start tracking files interactively |
| `git add .` |  Start tracking all untracked files in my current directory |
| `git add *` |  Start tracking all untracked files |
| `git add *.c` |  Start tracking all untracked with a `.c` suffix  |
|  |  |
| `git add <modified_file>` |  Stage the `<modified_file>` (i.e., add it to the index or the "staging area") |
| `git add <file_1> <file_2>` | Stage the two *modified* files -- `<file_1>`, `<file_2>` |
| `git add -i` |  Stage all modified files interactively |
| `git add .` |  Stage all modified files in my current directory |
| `git add *` |  Stage all modified files in my working directory |
| `git add *.c` |  Stage all modified files in my working directory starting with a `.c` |

---

# git commit

| Syntax | Description |
| ------ | ----------- |
| `git commit` | Commit all my staged files (with a message from my `core.editor`) |
| `git commit -m <msg>` | Commit all my staged files with `<msg>` |
| `git commit --amend` | Amend my previous commit message (use a message from my `core.editor`) |
| `git commit --amend -m <msg>` | Amend my previous commit message, use `<message>` instead |
| | |
| `git commit -a` | Stage & commit all my modified files (with a message from `core.editor`) |
| `git commit -a -m <msg>` | Stage & commit all my modified files with `<msg>` |

Note: `git commit -a` won't start tracking files. So if you're in a rush, don't
forget to tell Git it should track them!

---

# git clone 

| Syntax | Description |
| ------ | ----------- |
| `git clone <url>` | Clone a repo from `<url>` (..into a new working directory named like the last word in the `<url>` or the word before the `.git` prefix) |
| `git clone <url> <dir/>` | Clone the repo from `<url>` into `<dir/>` |

---

# git diff 

| Syntax | Description |
| ------ | ----------- |
| `git diff` | Show me all unstaged changes |
| `git diff <file>` | Show me all unstaged changes in `<file>` |
| `git diff --staged` | Show me all staged changes that will be part of my next commit |
| `git diff --cached` | Show me all staged changes that will be part of my next commit |
| `git diff --stat` | Give me a brief summary of all changes |
| `git diff <commit>` | Show me all changes sind a given commit `<file>` |
| `git diff <commit_1> <commit_2>` | Show me all changes between `<commit_1>` and `<commit_2>` |
| `git diff <commit> <file>` | Show me all changes since a given `<commit>` to a given `<file>` |
| `git diff <tag>` | Show me all changes since a `<tag>`-ed commit |

---

# git rm

| Syntax | Description |
| ------ | ----------- |
| `git rm <file>` | Remove this unstaged `<file>` from my WD |
| `git rm <pattern>` | Remove all unstaged files from my WD that match the `<pattern>` |
| `git rm \*` | Remove all unstaged files from my WD |
| `git rm --cached <file>` | Stop tracking this `<file>` (i.e., remove the `<file>` from the staging area, but keep it in my WD | 
| `git rm -f <file>` | Remove this staged `<file>` from my WD |

---

# git mv 

| Syntax | Description |
| ------ | ----------- |
| `git mv <bad_file> <good_file>` | Rename the `<bad_file>` to `<good_file>` |
| `git mv <file> </somedir/else/file>` | Move the `<file>` to `</somedir/else/file>` |

---

# git log

| Syntax | Description |
| ------ | ----------- |
| `git log` | Show me all commit logs |
| `git log -<n>` | Show me each of the last `<n>` commit logs  |
| `git log -1` | Show me the last commit log  |
| `git log -1 HEAD` | Show me the last commit log of the `current` branch (i.e.: indicated by `HEAD`) |
| `git log -p` | Show me the patch introduced with each commit (i.e., the within-file differences) |
| `git log -<n> -p` | Show me the patch introduced in each commit for each of my last `<n>` commit logs |
| `git log --stat` | Show me the commit-log statistic (i.e., if a file changed; and if so the lines added/removed `++++/---`) |
| `git log --shortstat` | Show me a short commit-log statistic (i.e., only the changed/insertions/deletions line from the `--stat` command )
| `git log --pretty=oneline` | Show me all commit logs in a prettified one-line format (e.g., abbreviated SHA-1 hashes) |
| `git log --oneline` | Show me all commit logs in a one-line format (e.g., abbreviated SHA-1 hashes) |
| `git log --graph` | Show me all commit logs and add an ASCII graph for the branch and merge history to the commit log history |
| `git log --decorate` | Show me all references (e.g., tags, branches, etc.) in addition to the commit logs |
| `git log --oneline --graph` | Show me all commit logs in a one-line format and add an ASCII graph for the branch and merge history |
| `git log --oneline --decorate --graph --all` | Show me an all-in-one supple commit-log output (..look above for details) |
|  |  |
| `git log --since="<date>"` | Show me all commit logs since `<date>` (e.g. `1 year 2 monts 3 weeks, 4 days`) |
| `git log --since <date>` | Show me all commit logs since `<date>` (e.g. `2.weeks, 2008-03-22"`) |
| `git log --after="<date>"` | Show me all commit logs after `<date>` |
| `git log --after <date>` | Show me all commit logs since `<date>` |
| `git log --until="<date>"` | Show me all commit logs until `<date>` |
| `git log --until <date>` | Show me all commit logs until `<date>` | 
| `git log --before="<date>"` | Show me all commit logs before `<date>` |
| `git log --before <date>` | Show me all commit logs until `<date>` | 
|  |  |
| `git log -S <string>` | Show me only commits where a `<string>` within the code changed (e.g., to monitor the changes of a function ) |
| `git log --grep <string>` | Show me only commit messages containing `<string>` |
| `git log -- <path/to/file>` | Show me only commit logs for a `<(path/to/)file>`  |
|  |  |
| `git log --author='<author>'` | Show me only commit from `<author>`  |
| `git log --committer='<author>'` | Show me  only commit from `<committer>`  |

---

# git restore (git reset) 

| Syntax | Description |
| ------ | ----------- |
| `git reset HEAD <file>` | Unstage this staged `<file>` |
| `git restore --staged <file>` | Unstage this staged `<file>` |
| | |
| `git restore <file>` | Unmodify this modified `<file>` |

---

# git remote 

| Syntax | Description |
| ------ | ----------- |
| `git remote` | Show me the remote shortnames |
| `git remote -v` | Show me the remote shortnames & the remote urls  |
| `git remote -vv` | Show me which tracking branches are set |
| `git remote show <remote>` | Give me extensive info about `<remote>` (i.e., HEAD, remote references, remote branch(es), tracking branch(es), push & pull info) |
| | |
| `git remote add <remote> <url>` | Add the `<remote>` under `<url>` |
| `git remote rename <old_remote> <new_remote>` | Rename the `<old_remote>` to `<new_remote>` (Note: does also change the names of remote-tracking branches) |
| `git remote remove <remote>` | Remove the `<remote>` |

---

# git fetch

| Syntax | Description |
| ------ | ----------- |
| `git fetch` | Fetch all info (from the specified remote tracking branch, see: `fetch URL`) |
| `git fetch <remote>` | Synchronize my localdb with `<remote>` |
| `git fetch ; git rebase <remote>/<branch>` | Rebase on top of force-pushed rebase work on `<remote>/<branch>` (I.e.: if someone force pushes changes that overwrote your work -- tries to apply them on top!) |

---

# git pull 

| Syntax | Description |
| ------ | ----------- |
| `git pull` | Fetch & merge all info (from the specified remote tracking branch, see `fetch URL`)  |
| `git pull <remote>` | Fetch all changes from `<remote>` and merge it into my localdb |
| | |
| `git pull --rebase <remote>` | Fetch all changes from `<remote>` and rebase them on my localdb |
| `git pull --rebase <remote>/<branch>` | Rebase on top of force-pushed rebased work on <remote>/<branch> (I.e.: if someone force pushes changes that overwrote my work -- tries to apply it on top!) |

---


# git push 

| Syntax | Description |
| ------ | ----------- |
| `git push` | Push my local changes (from `current` into `upstream` branch -- i.e.: remote/branch)  |
| `git push <remote> <branch>` | Push my local changes from `<branch>` into `<remote>/<branch>`  |
| `git push <remote> <local_branch>:<branch>` | Push my changes from `<local_branch>` into a differently named `<remote>/<branch>` |
| | |
| `git push --tags` | Push my local tags (from `current` into `upstream` branch -- i.e.: remote/branch)  |
| `git push <remote> <tag>` | Push the local `<tag>` into `<remote>` |
| `git push <remote> --tags` | Push all my local tags (`refs/tags`) into `<remote>` |
| | |
| `git push <remote> --delete` | Delete all my locally removed tags on `<remote>`, too (after a `git tag -d...`)   |
| `git push <remote> --delete <tag>` | Delete my locally removed `<tag> `on `<remote>`, too   |
| `git push <remote> --delete :refs/tags/<tag>` | Delete my locally removed `<tag> `on `<remote>`, too   |
| | |
| `git push --set-upstream <remote> <good_branch>` | Rename "bad_branch" to `<good_branch>` on `<remote>`, too (i.e., after doing `git branch --move <bad_branch> <good branch>`, and before doing `git push <remote> --delete <bad_branch>`) |
| `git push -u <remote> <good_branch>` | Rename "bad_branch" to `<good_branch>` on `<remote>`, too (i.e., after doing `git branch --move <bad_branch> <good branch>`, and before doing `git push <remote> --delete <bad_branch>`) |
| | |
| `git push --force <remote>` | Force to push all changes into `<remote>` |
| `git push <remote> +<branch>` | Force to push changes into a particular `<remote>/<branch>` |

| `git push <remote> --delete <branch>` | Delete the `<remote>/<branch>` |
| `git push <remote> --delete <tags>` | Delete the `<remote>/<tags>` on remote |

---

# git checkout 

| `git checkout -- <file>` | Unmodify the modified `<file>` |
| | |
| `git checkout <tag>` | Checkout the versions of files the `<tag>` is pointing to (Important: Puts you in the detached HEAD state)|
| `git checkout <branch>` | Checkout the `<branch>` | 
| `git checkout -b <branch>` | Create and checkout the `<branch>` | 
| `git checkout -b <branch> <tag>` | Checkout the versions of files `<tag>` is pointing to in `<branch>` |
| | |
| `git checkout --track <remote>/<branch>` | Create and checkout `<branch>` after setting it up to track `<remote>/<branch>` |
| `git checkout -b <branch> <remote>/<branch>` | Create and checkout `<branch>` after setting it up to track `<remote>/<branch>` (Note: Helpful if `<branch>` and `<remote>/<branch>` are named differently) |

---

# git switch 

| Syntax | Description |
| ------ | ----------- |
| `git switch -`  | Switch back to my previous branch |
| | |
| `git switch <branch>` | Checkout the `<branch>` | 
| `git switch <tag>` | Checkout how my files looked like when they were `<tag>`ed (Important: Puts you in the detached HEAD state)|
| `git switch <remote>/<branch>` | Check out how my `<remote><branch>` looked like (..the last time I communicated with it) | 
| | |
| `git switch -c <branch>` | Create a new `<branch>` and switch to it | 
| `git switch -c <branch> <tag>` | Checkout the versions of files `<tag>` is pointing to in a new `<branch>` |
| | |
| `git switch --track <remote>/<branch>` | Create & switch to `<branch>` after setting it up to track `<remote>/<branch>` |
| `git switch -c <branch> <remote>/<branch>` | Create & switch to `<branch>` after setting it up to track `<remote>/<branch>` (Note: Helpful if `<branch>` and `<remote>/<branch>` are named differently) |

---

# git tag 

| Syntax | Description |
| ------ | ----------- |
| `git tag` | Show me all tags (in the current repo) |
| `git tag -l <pattern>` | Search for tags that include `<pattern>`|
| | |
| `git tag <tag_lw>` | Create a lightweight `<tag_lw>` (for the latest commit)  |
| `git tag -a <tag>` | Create an annotated `<tag>` (for the latest commit; i.e., SHA-1 hash; tagger name, email, date; tagging message; GPG signature) |
| `git tag -a <tag> <commit>` | Create an annotated `<tag>` for a particular `<commit>` |
| `git tag <tag_lw> <commit>` | Create a lightweight `<tag_lw>` for a particular `<commit>`  |
| | |
| `git tag -d <tag>` | Delete the `<tag>` |

---

# git show 

| Syntax | Description |
| ------ | ----------- |
| `git show <object>` | Shows info about the `<object>` |
| `git show <tag>` | Shows info about the `<tag>` (i.e., SHA-1 hash; tagger name, email, date; tagging message; GPG signature) |

---

# git ls-remote

| Syntax | Description |
| ------ | ----------- |
| `git ls-remote <remote>` | Show me all remote references |

---

# git branch 

| Syntax | Description |
| ------ | ----------- |
| `git branch`| Show me local branches |
| `git branch --all`| Show me all branches (i.e.,local & remote tracking branches) |
| `git branch -v`| Show me all branches & their last commit |
| | |
| `git branch -vv`| Show me which tracking branches are set up |
| | |
| `git branch <branch>`| Create a new `branch` |
| `git branch -d <branch>`| Delete the `branch` |
| `git branch --move <bad_branch> <good branch>`| Rename `<bad_branch>` to `<good_branch>` |
| `git branch --move master main` | Rename `master` to `main` (i.e., before doing `git push --set-upstream <remote> main` and `git push <remote> --delete master`) |
| | |
| `git branch --merged`| Show me all branches that have merged into the `current` branch yet | 
| `git branch --merged <branch>`| Show me all branches that have merged into `<branch>` yet |
| `git branch --no-merged`| Show me all branches that have not merged into the `current` branch yet |
| `git branch --merged <branch>`| Show me all branches that have merged into `<branch>` yet | 
| | |
| `git branch -u <remote>/<branch>`| Set up `<branch>` to track `<remote>/<branch>` | 
| `git branch -u <remote>/<branch> <branch>`| Set up `<branch>` to track `<remote>/<branch>` (Note: helpful if the branch and the remote branch are named differently) |

---

# git merge

| Syntax | Description |
| ------ | ----------- |
| `git merge <topic_branch>`| Merge a `<topic_branch>` into my `current` branch (i.e.: indicated by `HEAD`) |
| `git merge <topic_branch> <base_branch>`| Merge a `<topic_branch>` into `<branch>` |

---

# git mergetool

| Syntax | Description |
| ------ | ----------- |
| `git mergetool` | Resolve a merge conflict graphically |

---

# git rebase

| Syntax | Description |
| ------ | ----------- |
| `git rebase <base_branch>` | Rebase patches of my `current` branch onto `<base_branch>` (Note: after doing a `git switch current`) |
| `git rebase <base_branch> <topic_branch>` | Rebase patches of a `<topic_branch>c` onto the `<base_branch>` |
| `git rebase --onto <base_branch> <branch> <another_branch> <topic_branch>` | Rebase patches that are unique to `<topic_branch>` -- i.e., not in `<another_branch>` -- and rebase them onto the `<base_branch>`. 
| `git rebase <remote>/<branch>` | Rebase on top of force-pushed rebase work on <remote>/<branch> (i.e., if someone force pushes changes that overwrote your work -- tries to apply them on top!)

---

# git mine

Some shortcuts I find useful!

| Syntax | Description |
| ------ | ----------- |
| `git unstage <file>` | `git reset -- HEAD <file>` |
| `git unstage <file>` | `git restore --staged <file>` |
| `git unmodify <file>` | `git restore <file>` |
| `git untrack` | `git rm --cached <file>` | 
| `git last` | `git log -1 HEAD` | 
| `git logcial` | `git log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit` | Alias for a log(ical) commit history output |
| `git visual` | `!gitk` | Alias for a visual git interface | 
| `git vivid` | `!git gui` An alternative to `gitk` | 

You can add the `logical` alias to your `.gitconfig` using by either using `git
config --global alias.<shorty> <command>. ` or adding `logical = log --color
--graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)
%C(bold blue)<%an>%Creset' --abbrev-commit` manually -- under `[alias]`-- to
your git configuration file.

---

# Protocols

Note: bare repositories are the collaborative element of the Git-verse. More
specifically, it is the centralized point that makes its content
"distributable" across units. In terms of your local working directory it just
includes the contents of your project???s `.git`. In order to communicated with
the remote repository, you have to chose a protocol.

## Protocols

### Local Protocol

```
/srv/git/project.git
```

**Example Use**

```
git remote add local_proj /srv/git/project.git
git push local_proj master
```

- Pros: Easy to set up!
- Cons: 
    - Often slower than SSH
    - Careless user can easily delete internal files!

Side note: The remote repo is in another directory on the same host. It is
useful if every on the team has access to a shared file system (e.g., NFS
mount)

### (Smart) HTTP

```
https://<url>/project.git
```

**Example Use**

```
git remote add origin https:// /srv/git/project.git
git push local_proj master
```

- Pros
    - Single URL for all types of access!
    - Anonymous access for open source projects!
    - Authentication with username and passwort
    - No need to generate SSH keys
    - No need to bring SSH keys to the server before you can interact with it.
- Cons: Sometimes harder to set up than SSH

Side note: Use together with a credential helper like KeyChain, etc. Than it is
maybe the most elegant way to process content.

### SSH 

formulae:

```
ssh://[user@]server/project.git
[user@]server:project.git
```
**Example Use**

```
git remote add origin git@github.com:sbissantz/Rmisc.git
git push origin master

git remote add origin ssh://steven@139.17.2.1/data/crucnhy_doku.git
git push origin master
```

- Pros
    - Easy to set up!
    - SSH daemons are common place!
    - Security! (encrypted & authenticated)
    - Efficiency! (compact data transfer)
    - No need to bring SSH keys to the server before you can interact with it.
- Cons: No anonymous access! (SSH key is obligatory)

### Git Protocol

A special daemon dedicated to part 9418. Does not require authentication and is
thus faster than SSH, since it don't need to encrypt files.

- Pros: Fastest network transfer protocol available!  
- Cons: Hardest to set up! (e.g., `git-daemon-export-ok` file, `systemd/xinted`, firewall access)




