<a href="https://golang.org"><img src="https://golang.org/lib/godoc/images/go-logo-blue.svg" align="left" width="100px"></a>

## Install Go on Raspberry Pi

<br>
<br>

### Download the lastest ARMv6 Linux package using `wget`

https://golang.org/dl/

ex.
```
wget https://go.dev/dl/go1.18.1.linux-armv6l.tar.gz
```

### Extract it to /usr/local

```
sudo tar -C /usr/local -xzf go1.18.1.linux-armv6l.tar.gz
rm go1.18.1.linux-armv6l.tar.gz
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
```

### Update shell:

```
source .profile
```

### Confirm installation

```
go version
```

### Install a Go Package to Create Go Folders

```
go install github.com/owenthereal/ccat@latest
```

`ccat` is a nice little package works like `cat`, but with color.
