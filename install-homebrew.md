<a href="https://docs.brew.sh/Homebrew-on-Linux"><img src="https://brew.sh/assets/img/linuxbrew.png" align="left" width="100px"></a>

## Install Homebrew on Raspberry Pi

<br>

```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"
```

```
$ test -d ~/.linuxbrew && eval $(~/.linuxbrew/bin/brew shellenv)
$ test -d /home/linuxbrew/.linuxbrew && eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)
$ test -r ~/.bash_profile && echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.bash_profile
$ echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.profile
```

Now you can install packages like [`brew install ccat`](https://github.com/jingweno/ccat)
