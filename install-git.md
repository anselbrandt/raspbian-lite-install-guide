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
$ git config --global user.email yourname@mail.com
$ git config --global core.editor nano
$ git config --global 
```

### Global .gitignore file

```
$ touch ~/.gitignore
$ nano ~/.gitignore
```

Sample `.gitignore` contents:

```
.idea/
.vscode/
node_modules/
build
.DS_Store
.AppleDouble
*.tgz
my-app*
template/src/__tests__/__snapshots__/
lerna-debug.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
/.changelog
.npm/
yarn.lock
```

### Confirm Global Config Values

```
$ git config --list
```
