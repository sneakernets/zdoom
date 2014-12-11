ZDoom for Raspberry Pi
=====

ZDoom is one of the most popular Doom source ports. This is an effort to bring that port to the Raspberry Pi. There is no FMOD required for sound, and it supports most EAX effects.

##Requirements

You need:

* Raspberry Pi with Raspbian Stable
* OpenAL dev libraries
* SDL libraries
* cmake 2.4 or greater
* gcc (4.x recommended)

Everything else is provided in the source tree.

##Caveats

This is a stripped down version of ZDoom. Some features will not exist, like hardware 2D support. Everything else should work. I have tested all Doom IWADS and they work.

If the game slows down and becomes choppy after sounds play, it is likely OpenAL. To fix this, reduce the number of max sounds to **8**. If this still does not solve the problem, create an `.alsoftrc` in your home dir and type:

```
[alsa]
mmap = false
```

Framerates are generally very good, playable in X11 but blazingly fast with Raspberry Pi's framebuffer, as it is hardware accelerated video. If you play in framebuffer mode, you MUST use 640x480. Thankfully it is default in ZDoom, so there are no issues with this. Only change video modes in X11!

**NOTE:** This was originally based on the git version of zdoom as of December 10, 2014. Any changes to ZDoom since then will be merged, but not at the speed of zdoom master. If there is a new feature in ZDoom in the future that hasn't been merged, contact me through Issues and I'll resolve it.

##Credits

Shoutouts go out to:
Chris/KCat from ZDoom Forums for starting work on the OpenAL port of ZDoom. Without it, sound would not have been possible.
Blzut3 and `#doom-tech` on OFTC for comments and suggestions.
Quasar for finding the humor of ZDoom running without FMOD.
id Software for making Doom

This was originally "released" on Doom's 21st birthday, but time restraints made this release a day late. Oops!
