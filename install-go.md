<a href="https://golang.org"><img src="https://golang.org/lib/godoc/images/go-logo-blue.svg" align="left" width="100px"></a>

## Install Go on Raspberry Pi

<br>
<br>

### Download the lastest ARMv6 Linux package using `wget`

https://golang.org/dl/

ex.
```
wget https://golang.org/dl/go1.15.8.linux-armv6l.tar.gz
```

### Extract it to /usr/local

```
sudo tar -C /usr/local -xzf go1.15.8.linux-armv6l.tar.gz
rm go1.15.8.linux-armv6l.tar.gz
```

### Add to path

```
sudo nano .profile
```

Add the following:

```
PATH=$PATH:/usr/local/go/bin
GOPATH=$HOME/go

PATH=$PATH:/home/pi/go/bin
source "$HOME/.cargo/env"
```

### Install a Go Package to Create Go Folders

```
go get -u github.com/owenthereal/ccat
```

`ccat` is a nice little package works like `cat`, but with color.

Update shell:

```
source .profile
```

### Confirm installation

```
go version
```
