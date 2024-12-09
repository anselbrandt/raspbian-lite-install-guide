# Raspberry Pi 5

USB audio interface may be card 0

# Enabling USB Audio

After connecting USB audio interface, run `aplay -l` to confirm card number (external hardware should be card 1)

Run:

```
sudo nano /usr/share/alsa/alsa.conf
```

Look for the following lines:

```
defaults.ctl.card 0
defaults.pcm.card 0
```

Change default audio card from 0 (internal) to 1 (external):

```
defaults.ctl.card 1
defaults.pcm.card 1
```

Update `alsa` options:

```
sudo nano /etc/asound.conf
```

Add the following:

```
pcm.!default  {
 type hw card 1
}
ctl.!default {
 type hw card 1
}
```

Test playback with any wav file:

```
aplay sample.wav
```
