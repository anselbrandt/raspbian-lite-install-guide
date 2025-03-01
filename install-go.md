<a href="https://golang.org"><img src="https://go.dev/images/go-logo-blue.svg" align="left" width="100px"></a>

## Install Go on Raspberry Pi

<br>
<br>

### Remove previous version

```
sudo rm -rf /usr/local/go
```

### Download the lastest ARM64 Linux package using `wget`

(If you only have 32-bit Raspbian installed, download the ARMv6 package)

https://golang.org/dl/

ex.
```
wget https://go.dev/dl/go1.23.4.linux-arm64.tar.gz
```

### Extract it to /usr/local

```
sudo tar -C /usr/local -xzf go1.23.4.linux-arm64.tar.gz
rm go1.23.4.linux-arm64.tar.gz
```

### Add to path

```
sudo nano .profile
```

Add the following:

```
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
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

### ~~Install Go serve~~

~~Serves static files in any given accessible directory until you hit `Ctrl-C`~~

~~`go install github.com/philippgille/serve@latest`~~

Install Node.js `serve` from Vercel:
```
npm install -g serve
```
