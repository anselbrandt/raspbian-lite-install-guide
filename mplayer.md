# mplayer

sudo apt install mplayer

aplay -l

Take note of card number of USB audio device

sudo nano /usr/share/alsa/alsa.conf

Change 0 to the number of your device

```
defaults.ctl.card 0
defaults.pcm.card 0
```

mplayer file.mp3
