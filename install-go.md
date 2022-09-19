<a href="https://golang.org"><img src="https://go.dev/images/go-logo-blue.svg" align="left" width="100px"></a>

## Install Go on Raspberry Pi

<br>
<br>

### Download the lastest ARM64 Linux package using `wget`

(If you only have 32-bit Raspbian installed, download the ARMv6 package)

https://golang.org/dl/

ex.
```
wget https://go.dev/dl/go1.18.2.linux-arm64.tar.gz

or

wget https://go.dev/dl/go1.19.1.linux-armv6l.tar.gz
```

### Extract it to /usr/local

```
sudo tar -C /usr/local -xzf go1.18.2.linux-arm64.tar.gz
rm go1.18.2.linux-arm64.tar.gz

or

sudo tar -C /usr/local -xzf go1.19.1.linux-armv6l.tar.gz
rm go1.19.1.linux-armv6l.tar.gz
```

### Add to path

```
sudo nano .profile
```

Add the following:

```
export GOPATH="$HOME/go"
PATH="$GOPATH/bin:$PATH"
PATH=$PATH:/usr/local/go/bin
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
