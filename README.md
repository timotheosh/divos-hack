# divos-hack

## Issues: Will not start without OpenGL 4, and has issues with Mesa

Most resent bug discussed here: https://bugs.freedesktop.org/show_bug.cgi?id=93551

Last time, I got this to work on my Laptop using primusrun. I had to get the divos-hack.c file, and compile it into a library. https://bitbucket.org/darktjm/divos-hack/src/master/divos-hack.c

Put the library in the game directory for Divinity and modify the runner.sh script accordingly:
``` shell
#!/bin/sh

DIR="/home/thawes/.steam/steam/steamapps/common/Divinity Original Sin Enhanced Edition"

PRIMUS_libGL=/usr/lib/x86_64-linux-gnu/libGL.so.1 LD_PRELOAD=divos-hack.so LD_LIBRARY_PATH="${DIR}" primusrun "${DIR}"/EoCApp
```
I also noticed that this shim made it possible to play the game on the normal Intel card as well. I am wondering if a similar shim will appear for Nvidia cards, where I might get back better performance... time will tell.
