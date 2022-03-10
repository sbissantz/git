# Becoming up-to-date!

If you're part of a multi-user project that centralizes its work on a remote
repository, you will stumble across `ahead` and `behind`. `ahead` means you
missed to push your local patches. `behind` is the opposite; the remote
contains work you haven't pulled in yet. The main problem with both indicators
is -- they are often outdated. Being capable to update them is thus a helpful
thing to know. 

```
git fetch --all 
git branch -vv
```

