### Git and Github configuration
* Git configuration on your local system.

```bash
touch .gitconfig
```


```cnf
[user]
email = example@mail.com
name = example
password = github token
[init]
defaultBranch = master
[safe]
directory = project path
[credential]
helper = store
```

### Git and GitHub config (with Token)
```zsh
touch .git-credentials
vi .git-credentials
```

```vim
https://username:ghp_token@github.com
```
