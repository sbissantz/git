## Rstudio setup

Many of us just want to keep track of their R-files and not make Git a second
home (as I did). That's all right. RStudio lends you a hand with that. Open the
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

