## Installing Node with NVM on Raspberry Pi

## *** Node.js must be installed manually on Pi Zero/Pi Zero W and Rapsberry Pis earlier than 3b

Many Node packages for Raspberry Pi hardware, such as [`nodeimu`](https://www.npmjs.com/package/nodeimu) have not been updated to work with the most recent versions of Node, so being able to easily switch between versions with NVM is helpful.

Check the [nvm github](https://github.com/nvm-sh/nvm) for the most recent version.

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```

Close and reopen your terminal to start using nvm or run the following to use it immediately:

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```

\* If you want to install `nodeimu` I have gotten it to work on Node 8.10.0 with node-gyp 4.0.0. Install with `npm install nodeimu`. Manually building from `github` doesn't seem to work.

\* `nodeimu` seems to have been updated to work with any current version of Node.

### *** Manual Install

Get the latest version for `armv61` from https://unofficial-builds.nodejs.org/download/release/

Install NVM as above.

Edit `.profile`:

```
sudo nano .profile
```
Add the following:
```
export NVM_NODEJS_ORG_MIRROR=https://unofficial-builds.nodejs.org/download/release
```
Reload `.profile`

```
source ~/.profile
```

Then:
```
nvm ls-remote
```

In a browser, check to confirm the version you want has been built for `armv61`

Then `nvm install` that version, ex. `nvm install v15.8.0`
