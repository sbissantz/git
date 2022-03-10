# Modification D-day!

Git is pretty tolerant if you messed it up. That's good news, because there are
multiple steps of escalation on which you can intervene. Let's move through
them case by case:

## I. Staged a file by mistake!

Don't worry! you can use simple use: 

```
git restore --staged
```

Note: As I have bad memory and always confuse when to put the `--staged` flag
at the `restore` command, I created an alias. I use:

```
git unstage
```

## II. Modified accidentally!

So what! 

```
git unmodify 
```

## III. Pushed inadvertently!

```
git untrack 
```

## IV. Really 'fogd' it up!

However, if you did completely mess up your repo and there is no way to get you
out there in one piece do *not* abandon hope. Drop all your local changes and
commits, fetch the latest history from the server and point your local master
branch at it.

```
git fetch origin 
git reset --hard origin/master
```







