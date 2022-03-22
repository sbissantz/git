# Put a remote repository on the Server

Did you start a new project? Of course, you want to commission Nanny McGit to
take care of it. It's pretty simple. Initialize a bare Git repository and put
it on the server. If you know that others will contribute to your project, you
can give the assigned group writing access by adding the `--shared` flag. 

```
git init --bare --shared project.git
scp -r project.git <user>@<IP>:/path/to/dir.git
```

Now your contributors can simple hack the snippet below into their console to
download your repo:

```
git clone project.git <user>@<IP>:/path/to/dir.git
```

Tidbit: If you have an exact idea about file permissions use `git init --bare
--shared=<filemodebit(s)> myrepo.git`. For example, to roughly mimic the result
of `git init --bare --shared` type `git init --bare --shared=0660 myrepo.git`.
