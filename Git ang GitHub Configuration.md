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
```sh
touch .git-credentials
vi .git-credentials
```

```js
https://username:ghp_token@github.com
```
