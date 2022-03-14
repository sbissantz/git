# Git Guis

## gitk & git gui

First, run `brew install git-gui`. The code will use the package manager
`homebrew` to install `git gui`and companions. After the installation finished,
test that you can run both apps--`gitk` and `git gui`. If so, I recommend you
setting up two aliases. Using an alias has the benefit of being more time
efficient. You can simple open a terminal and type the alias and poof, the
secret door to the realm of Git-dreams opens. I would also suggest to use
expressive names, because they are easier to remember plus (often) easier to
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
not with BitBucket, let's say, you will get a pretty nice handy GUI for Git.
Wanna give it a try? Then open a console and use Homebrew. The spell is:

`brew install --cask github`

## Rstudio


