<a href="https://www.raspberrypi.org/downloads/raspbian/"><img src="https://www.raspberrypi.org/app/themes/mind-control/images/application/header/home-link.svg" align="left" width="100px"></a>

<br>

## Raspbian Lite Install Guide

<br>

This is a step-by-step guide for installing Raspbian Lite onto a headless Raspberry Pi from a Mac. If everything works, your Raspberry Pi will:

  - connect to your WiFi network on boot
  - be visible in Finder as an SMB share
  - allow SSH login at `username@raspberry-pi-name.local`

### 1. Download Raspbian Lite

https://www.raspberrypi.org/downloads/raspbian/

### 2. Download and install balenaEtcher

https://www.balena.io/etcher/

You don't need to use balenaEtcher, but it's so much simpler than typing out commands.

### 3. Flash your SD card with the downloaded Raspbian image using balenaEtcher

### 4. Remove/Reinsert or Mount your newly flashed SD card (still on your Mac)

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
control-o, control-x to save changes and exit nano.

Unmount and remove your SD card, insert into your Raspberry Pi and power it on.

### 5. Connect to your Raspberry Pi

```
$ ssh pi@raspberrypi.local
```

The default password will be `raspberry`

