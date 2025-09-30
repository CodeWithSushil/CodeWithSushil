### Git and Github configuration
* Git configuration on your local system.

```bash
touch .gitconfig
```


```cnf
[user]
    name = Your Name
    email = your@email.com
    signingkey = ABCDEF1234567890   # (optional, if you use GPG/SSH signing)

[core]
    editor = nvim
    autocrlf = input
    excludesfile = ~/.gitignore_global

[color]
    ui = auto

[commit]
    template = ~/.gitmessage
    gpgsign = true                  # sign commits by default (if you use GPG)

[merge]
    tool = nvimdiff
    ff = only

[mergetool]
    prompt = false
    keepBackup = false

[pull]
    rebase = true

[rebase]
    autoStash = true

[diff]
    colorMoved = zebra

[alias]
    st = status -sb
    co = checkout
    br = branch
    cm = commit -m
    lg = log --oneline --graph --decorate --all
    amend = commit --amend --no-edit
    pl = pull --rebase
    ps = push

[credential]
    helper = manager-core           # or osxkeychain / libsecret depending on OS
```

### Git and GitHub config (with Token)
```sh
touch .git-credentials
vi .git-credentials
```

```js
https://example:ghp_token@github.com
```
