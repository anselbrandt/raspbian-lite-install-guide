<a href="https://docs.brew.sh/Homebrew-on-Linux"><img src="https://brew.sh/assets/img/linuxbrew.png" align="left" width="100px"></a>

## Install Homebrew on Raspberry Pi

<br>
<br>

Installing Homebrew requires that we first have `Git` installed:

```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install git
```

Now we can install Homebrew:

```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"
```

```
$ test -d ~/.linuxbrew && eval $(~/.linuxbrew/bin/brew shellenv)
$ test -d /home/linuxbrew/.linuxbrew && eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)
$ test -r ~/.bash_profile && echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.bash_profile
$ echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.profile
```

If `Homebrew` gives you any errors about `locale`, you may need to set `locale` and `languge` in `$ sudo raspi-config`

Now you can install packages like [`brew install ccat`](https://github.com/jingweno/ccat)

\*`ccat` requires `golang`, and Hombrew seems to have trouble installing Go, so you may need to `$ sudo apt-get install golang` first. Then, `brew install --ignore-dependencies ccat`
