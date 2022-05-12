# Setup git with SSH on the server 

## On the server side

On the server side of the moon: We first make `git` our new user on the server:

```
sudo adduser git
su git
```

Then we prepare its `.ssh` directory:

```
mkdir .ssh && chmod 700 .ssh
touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
```

Now its time to feed it with some public keys:

```
cat /tmp/id_rsa.john.pub >> ~/.ssh/authorized_keys
cat /tmp/id_rsa.josie.pub >> ~/.ssh/authorized_keys
```

After that we create the first project:

```
cd /srv/git
mkdir project.git
cd project.git
git init --bare
```

---

## On the user side

On my computer!

```
cd usrproject
git init
git add .
git commit -m "Initial commit"
git remote add origin git@gitserver:/srv/git/project.git
git push -u origin master
```

You can just clone the repo, too:

```
git clone git@gitserver:/srv/git/project.git
```

## On the other(s) side!

```
git clone git@gitserver:/srv/git/project.git
cd project
vim README
git commit -am 'Fix for README file'
git push origin master
```

---

## Restrictions

Now restrict the new user `git` to only Git-related things. This means no
normal shell access to the computer. But it is capable of getting a SSH
connection to push/pull:

```
cat /etc/shells   # see if git-shell is already in there. If not...
which git-shell   # make sure git-shell is installed on your system.
sudo -e /etc/shells  # and add the path to git-shell from last command

sudo chsh git -s $(which git-shell)
```

Let's double check, what happended if you try to SSH-shell on the server:

```
$ ssh git@gitserver
fatal: Interactive git shell is not enabled.
hint: ~/git-shell-commands should exist and have read and execute access.
Connection to gitserver closed.
```

But hold on! users can still use SSH port forwarding. Which means users can
access any host the git server is able to reach. If you don't like that, modify
the authorized_keys file and add ... to the end of *each* key!

`no-port-forwarding,no-X11-forwarding,no-agent-forwarding,no-pty`

Now Git network commands will still work just fine but the users won’t be able
to get a shell.

Note: Customize the message that users see if they try to SSH in like that. Run
`git help shell`.

