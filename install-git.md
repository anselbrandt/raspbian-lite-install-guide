<a href="https://git-scm.com"><img src="https://git-scm.com/images/logo@2x.png" align="left" width="100px"></a>

<br>

## Installing Git on Raspberry Pi

<br>

```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install git
```

### Configure Git Global Values

```
$ git config --global user.name "Your Name"
$ git config --global user.email your@email.com
$ git config --global core.editor nano
$ git config --global credential.helper 'store'
```

To save your password, `git clone` any random repo.

### Global .gitignore file

```
$ touch ~/.gitignore
$ nano ~/.gitignore
```

Add contents to your `.gitignore` file.

Sample `.gitignore` contents:

```
*.tgz
.DS_Store
.eslintcache
.env
.env.local
.idea/
.npm/
.vscode/
/.changelog
RTIMULib.ini
build
dist
lerna-debug.log
my-app*
node_modules/
npm-debug.log*
template/src/__tests__/__snapshots__/
yarn-debug.log*
yarn-error.log*
yarn.lock
```

`control-o`, `control-x` to save and exit.

Point `git` to your global .gitignore file

```
$ git config --global core.excludesfile ~/.gitignore
```

### Confirm Global Config Values

```
$ git config --list
```
