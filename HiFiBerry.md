<a href="https://www.hifiberry.com/docs/software/configuring-linux-3-18-x/"><img src="https://www.hifiberry.com/wp-content/themes/hifiberry/assets/images/hifiberry_logo.svg" width="300px"></a>

## Configure Raspberry Pi for Custom Sound Card

Insert and mount your SD card in your Mac or PC.

```
$ cd /Volumes/boot/
$ sudo nano config.txt
```

Remove the following line:

```
dtparam=audio=on
```

Add the following line:

```
dtoverlay=hifiberry-dacplus
```

(or whatever your soundcard happens to be called)

`control-o`, `control-x` to save and exit.

Install `mplayer`

```
sudo apt-get install mplayer
```

Play files:

```
mplayer filename
```
