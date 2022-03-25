# A quick way to setup git with SSH on the server 

```
sudo adduser git
su git
mkdir .ssh && chmod 700 .ssh
touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
cat /tmp/id_rsa.john.pub >> ~/.ssh/authorized_keys
cat /tmp/id_rsa.josie.pub >> ~/.ssh/authorized_keys
cd /srv/git
mkdir project.git
cd project.git
git init --bare
```

On my computer!

```
cd usrproject
git init
git add .
git commit -m "Initial commit"
git remote add origin git@gitserver:/srv/git/project.git
git push origin master
```

On the others computer

```
git clone git@gitserver:/srv/git/project.git
cd project
vim README
git commit -am 'Fix for README file'
git push origin master
```

---

You can easily restrict the git user account to only Git-related activities
with a limited shell tool called git-shell. If you set this as the git user
account’s login shell, then that account can’t have normal shell access to your
server.

```
cat /etc/shells   # see if git-shell is already in there. If not...
which git-shell   # make sure git-shell is installed on your system.
sudo -e /etc/shells  # and add the path to git-shell from last command

sudo chsh git -s $(which git-shell)
```

Now, the git user can still use the SSH connection to push and pull Git
repositories but can’t shell onto the machine. If you try, you’ll see a login
rejection like this:

```
$ ssh git@gitserver
fatal: Interactive git shell is not enabled.
hint: ~/git-shell-commands should exist and have read and execute access.
Connection to gitserver closed.
```

At this point, users are still able to use SSH port forwarding to access any
host the git server is able to reach. If you want to prevent that, you can edit
the authorized_keys file and prepend the following options to each key you’d
like to restrict:

`no-port-forwarding,no-X11-forwarding,no-agent-forwarding,no-pty`


Now Git network commands will still work just fine but the users won’t be able to get a shell.

Customize the message that users see if they try to SSH in like that. Run git help shell
