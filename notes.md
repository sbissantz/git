# Notes

Was it is a remote repository in Git-ish?

A bare repo 

```
git init --bare <bare_repo> 
```

What is a bare repo? 
a Git repository that has no working directory. 

Note: The repository is only used as a collaboration point. A bare repository
is the contents of your project’s .git directory and nothing else.

## Protocols

### Local Protocol

The remote repository is in another directory on the same host. It is useful if
every on the team has access to a shared filesystem (e.g., NFS mount)

formula:

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

### (Smart) HTTP

```
https://<url>/project.git
```

**Example Use**

```
git remote add origin https:// /srv/git/project.git
git push local_proj master
```

Use together with a credential helper like KeyChain, etc. Than it is maybe
the most elegant way to process content.

- Pros
    - Single URL for all types of access!
    - Anonymous access for open source projects!
    - Authentication with username and passwort
    - No need to generate SSH keys
    - No need to bring SSH keys to the server before you can interact with it.
- Cons: Sometimes harder to set up than SSH

### SSH 

formulae:

```
ssh://[user@]server/project.git
git clone [user@]server:project.git
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

---




