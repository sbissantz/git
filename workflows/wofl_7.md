
# Modification D-day!

Git is pretty tolerant if you messed it up. That's good news because there are
multiple steps of escalation on which you can intervene. Let's move through
them case by case:

## I. Staged a file by mistake!

Don't worry! You can use simple use: 

```
git restore --staged <file>
```

Note: I have a bad memory and am always confused when to add the `--staged`
flag on the `restore` command. I created an alias, therefore. 

```
git unstage <file>
```

## II. Modified accidentally!

So what! Simple use:

```
git restore <file>
```

Note: For me, it is simpler to run: 

```
git unmodify <file>
```





## III. Pushed inadvertently!

If you have accidentally started tracking a file --shame on you!-- you can stop
it with the upcoming snippet. The snippet makes old Nanny McGit forget about
her rising offspring. Nevertheless, the file will stay in your working
directory (i.e., it won't be deleted).

```
git rm --cached <file>
```

I use a more literal alias: "Nanny McGit stop tracking the `<file>`"

```
git untrack <file>
```

## IV. Really 'food' it up!

However, if you messed up your repo completely -- and there is no way to get
you out there in one piece -- do *not* abandon hope. Drop all your local
changes and commits, fetch the latest history from the server and point your
local master branch at it.

```
git fetch origin 
git reset --hard origin/master
```


