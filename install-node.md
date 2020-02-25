## Installing Node with NVM on Raspberry Pi

Many Node packages for Raspberry Pi hardware, such as [`nodeimu`](https://github.com/rupnikj/nodeimu) (It compiles on 8.10.0) have not been updated to work with the most recent versions of Node, so being able to easily switch between versions with NVM is helpful.

Check the [nvm github](https://github.com/nvm-sh/nvm) for the most recent version.

```
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
```

Close and reopen your terminal to start using nvm or run the following to use it immediately:

```
$ export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```
