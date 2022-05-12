<a href="https://www.raspberrypi.org/downloads/raspbian/"><img src="https://www.raspberrypi.org/app/themes/mind-control/images/application/header/home-link.svg" align="left" width="100px"></a>

<br>

## Raspbian Lite Install Guide

<br>

# Raspberry Pi no longer has `pi` default user. A user must be configured while flashing SSD

See the following blog post for more info:

https://www.raspberrypi.com/news/raspberry-pi-bullseye-update-april-2022/

<br>

This is a step-by-step guide for installing Raspbian Lite onto a headless Raspberry Pi from a Mac. If everything works, your Raspberry Pi will:

  - connect to your WiFi network on boot
  - be visible in Finder as an SMB share
  - allow SSH login at `username@raspberry-pi-name.local`
  
  See the other files for installing:
  
  - [Git](https://github.com/anselbrandt/raspbian-lite-install-guide/blob/master/install-git.md)
  - [Homebrew](https://github.com/anselbrandt/raspbian-lite-install-guide/blob/master/install-homebrew.md)
  - [Node](https://github.com/anselbrandt/raspbian-lite-install-guide/blob/master/install-node.md)
  - [HiFiBerry](https://github.com/anselbrandt/raspbian-lite-install-guide/blob/master/HiFiBerry.md) or another soundcard

### 1. Download Raspbian Lite

https://www.raspberrypi.org/software/operating-systems/

### 2. Download and install Raspberry Pi Imager

https://www.raspberrypi.com/software/

### 3. Flash your SD card with the downloaded Raspbian image using balenaEtcher

### 4. Remove/Re-insert or Mount your newly flashed SD card (still on your Mac)

```
$ cd /Volumes/boot/
$ sudo touch ssh
$ sudo nano wpa_supplicant.conf
```

Paste in the following:

```
country=CA
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="your-wifi-network-name"
    psk="your-wifi-password"
}
```

Pay attention to wifi network name case.

`control-o`, `control-x` to save changes and exit nano.

Unmount and remove your SD card, insert into your Raspberry Pi and power it on.

### 5. Connect to your Raspberry Pi

```
$ ssh pi@raspberrypi.local
```

The default password will be `raspberry`

If you have trouble connecting to your Raspberry Pi, or have previously connected to it via SSH, you may need to clear out your `known_hosts` file in `~/.ssh`

### 6. Change the name of your Pi

```
$ sudo nano /etc/hosts
```

On the last line, change the name `raspberrypi` to whatever you like. If you have more than one Pi on your network, you will want to give them different names.

`control-o`, `control-x` to save and exit.

```
$ sudo nano /etc/hostname
```

Change the name `raspberrypi` to the same name you used above.

`control-o`, `control-x` to save and exit.

If you wish to change the default password, enter:

```
$ sudo raspi-config
```

Reboot your Pi:

```
$ sudo reboot
```

Reconnect to your Pi using new host name (and new password if you changed that)

```
$ ssh pi@new-host-name.local
```

### 7. Enable file sharing

```
$ sudo apt-get update
$ sudo apt-get install netatalk
```

Netatalk now installs with no default shares, which will result in a failed connection on your Mac.

You need to uncomment two lines in the Netatalk config file, and set default share to your `/home` folder:

```
$ sudo nano /etc/netatalk/afp.conf
```
Change the following:
```
;[Homes]
;basedir regex = /****
```
to:
```
[Homes]
basedir regex = /home
```

Restart Netatalk:

```
sudo systemctl restart netatalk
```

Now your Raspberry Pi should be visible in Finder under Network. If it isn't, or if it later fails to connect, quit Finder using the Activity Monitor. This will clear out the Finder Network cache.

### 8. Enable additional hardware, or install additional packages

Enable the Pi Camera under Interfacing Options in the Configuration Tool

```
$ sudo raspi-config
```

Test the Pi Camera:

```
$ raspistill -v -o test.jpg
```

## New Camera Interface

https://www.raspberrypi.com/documentation/accessories/camera.html

```
libcamera-still -o test.jpg
```

To load the `bcm2835-v4l2` driver:

```
$ sudo modprobe bcm2835-v4l2
```

To load the the `bcm2835-v4l2` driver on boot:

```
$ sudo nano /etc/modules
```

and add the following line:
```
bcm2835-v4l2
```

If you intend to use the audio output of your Pi, you may want to install something like,

```
$ sudo apt-get install mplayer
```

### 9. Sense HAT

Enable I2c in the Configuration Tool under Interfacing Options:

```
$ sudo raspi-config
```

```
$ sudo apt-get update
$ sudo apt-get install sense-hat
$ sudo reboot
```

If the LEDs on your Sense HAT remain on after rebooting, you may need to `$ sudo shutdown -h now` your PI, and change the `config.txt` settings using your Mac.

Once you have inserted and mounted your SD card:

```
$ cd /Volumes/boot
$ nano config.txt
```

Add the following to the very end of the file:

```
dtoverlay=rpi-sense
```

`control-o`, `control-x` to save and exit.

Unmount and remove your SD card from your computer and re-insert it in your Pi and power it on. The LEDs should now turn off after booting.
