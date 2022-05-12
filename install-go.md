<a href="https://golang.org"><img src="https://go.dev/images/go-logo-blue.svg" align="left" width="100px"></a>

## Install Go on Raspberry Pi

<br>
<br>

### Download the lastest ARMv6 Linux package using `wget`

https://golang.org/dl/

ex.
```
wget https://go.dev/dl/go1.18.2.linux-armv6l.tar.gz
```

### Extract it to /usr/local

```
sudo tar -C /usr/local -xzf go1.18.2.linux-armv6l.tar.gz
rm go1.18.2.linux-armv6l.tar.gz
```

### Add to path

```
sudo nano .profile
```

Add the following:

```
export GOPATH="$HOME/go"
PATH="$GOPATH/bin:$PATH"
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
