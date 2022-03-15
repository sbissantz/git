
# Git Guis

## gitk & git gui

First, run `brew install git-gui`. The code will use the package manager
`homebrew` to install `git gui`and companions. After the installation is
finished, test if you can run both apps--`gitk` and `git gui`. If so, I
recommend you set up two aliases. Using an alias has the benefit of being more
time-efficient. You can simply open a terminal and type the alias and poof, the
secret door to the realm of Git-dreams opens. I would also suggest using
expressive names because they are easier to remember plus (often) easier to
type. My aliases are the following two:

```
git config --global alias.visual '!gitk'
git config --global alias.vivid '!git gui'
```

    Note the exclamation mark (!). `!` is mandatory, because `gitk` is an external command. 

Hold on! There is even a simpler way to access Git graphically. If you managed
to run Git's GUI somehow you can click `Repository`in the upper left and then
select `Create Desktop Icon`. Neat! Since we can now easily run `git visual`
and `git gui` we can enjoy a visual git experience. Bon appetit!

## GitHub Desktop 

Another option is to use GitHub Desktop. If you're just using Git with GitHub,
not with, let's say, BitBucket you will get a pretty nice handy GUI for Git.
Wanna give it a try? Open a console and use Homebrew. The spell is:

```
brew install --cask GitHub
```

## Rstudio

Many of us just want to keep track of their R-files and not make Git a second
home, as I did. That's all right. RStudio lends you a hand with that. Open the
`Global Options` under `Tools`in the upper right of your screen. A pop-up
window opens. Select `Git/SVN`. First, you have to make sure, RStudio knows
where your public key is. Look at the `SSH RSA key`. Is there a path to a
directory and a file ending with `.rsa`? If so, great! You're almost done. If
not, click on the `Create RSA Key` button below and follow the instruction.
I'll meet you right hereafter.

Alright, we're done with the global options. Now we have to recruit Nanny McGit
for our project. Navigate to the `Project Options` under `Tools`. Select
`Git/SVN`. Great, now we gotta make sure to use Git. Choose `Git` in the
drop-down menu behind `Version control system`. In addition, Git must know
where to push; so we have to set the location of the remote repository.
Typically that's the `Origin`. If your repository is at GitHub use it with SSH
as part of good practice. An adapted version of the following formula will do
the job: `git@github.com:username/repo.git`. I have something like
`git@github.com/sbissantz/Rmisc.git` for my `Rmisc`repository.

