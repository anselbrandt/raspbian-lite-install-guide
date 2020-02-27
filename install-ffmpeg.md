## Install FFmpeg with h.264 on Raspberry Pi

First install h.264 encoder

```
$ git clone https://code.videolan.org/videolan/x264.git
$ cd x264
$ ./configure --host=arm-unknown-linux-gnueabi --enable-static --disable-opencl
$ make -j4
$ sudo make install
```

Then install FFmpeg

```
$ git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg
$ cd ffmpeg
$ ./configure --arch=armel --target-os=linux --enable-gpl --enable-libx264 --enable-nonfree
$ make -j4
$ sudo make install
```

You can test FFmpeg h.264 encoding if you have a sample file on your Pi

```
$ ffmpeg -i sample-input.h264 -vcodec copy sample-output.mp4
```
