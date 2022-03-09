
# Set it up! 

---

Let's start the series with the main settings to make you jump right off the
ground. First, we will cover the nuts and guts -- define our global user and
its email address. Then we will finish by rising git a little bit. More
specifically, we'll spice it with some additional nice-to-haves.

## Mandatory!

*These two are mandatory!* Git does always want to know who its dealing with.
So, as promised, we need to define your global user and the global user's email
address. Fortunately, it is as simple as...


```
git config --global user.name "Steven Marcel Bißantz" 
git config --global user.email bissantz@uni-landau.de
```

### Rise & Additionals!

*Those are nice to have!* We start by setting up a credential helper. A
credential helper makes git remember your passphrase so you don't need to enter
it each time you push local changes. Neat! Thereafter, we tame the SHA-1 40
character hexadecimal beast. Using only seven digits, we massively slim down
the output of the `git log` command, for example. And then? Well, I am a
(Neo-)Vim fanatic. Setting my editor to `nvim` is thus a must-have for me. Last
and least: the pulling default. I meet some people that love rebasing as their
default pulling strategy (i.e., instead of merging). A matter of taste and
circumstances; but I don't want to let it go under the table.

```
git config --global credential.helper cache
git config --global core.abbrev 7
git config --global core.editor nvim
git config --global pull.rebase true
```
