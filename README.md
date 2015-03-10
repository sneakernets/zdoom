ZDoom for Raspberry Pi and Pi 2
=====

ZDoom is one of the most popular Doom source ports. This is an effort to bring that port to the Raspberry Pi. There is no FMOD required for sound, and it supports most EAX effects.

##Requirements

You need:

* Raspberry Pi or Pi 2 with Raspbian Stable
* OpenAL dev libraries
* SDL2 libraries
* libev-dev and libuv-dev (NEEDED!)
* cmake 2.4 or greater
* gcc (4.x recommended)
* MPG123 dev libraries
* libsndfile dev libraries

Everything else is provided in the source tree.

**NEW!** If you don't want to compile SDL2 and you have a Pi 2, just use this version at http://malus.exotica.org.uk/~buzz/pi/sdl/ that works with dispmanx and GLES2. To use, install all packages in `sdl2/`. That's it!

If you still want to compile SDL2, I recommend downloading and using the Simple2D install script located at

`https://github.com/simple2d/simple2d/blob/master/simple2d.sh`
##Caveats

This is a stripped down version of ZDoom. Some features will not exist, like hardware 2D support. Everything else should work. I have tested all Doom IWADS and they work.

If the game slows down and becomes choppy after sounds play, it is likely OpenAL. To fix this, reduce the number of max sounds to **8**. If this still does not solve the problem, create an `.alsoftrc` in your home dir and type:

```
[alsa]
mmap = false
```

**NOTE:** As of the SDL2 inclusion, you need to make sure you have `libev-dev` and `libuv-dev` packages installed before compiling SDL2. 

This was originally based on the git version of zdoom as of March 6, 2015. Any changes to ZDoom since then will be merged, but not at the speed of zdoom master. If there is a new feature in ZDoom in the future that hasn't been merged, contact me through Issues and I'll resolve it.

##Credits

Shoutouts go out to:

- Chris/KCat from ZDoom Forums for starting work on the OpenAL port of ZDoom. Without it, sound would not have been possible.
- Blzut3 and `#doom-tech` on OFTC for comments and suggestions.
- Quasar for finding the humor of ZDoom running without FMOD.
- id Software for making Doom.
- John Romero, for being awesome.
- Mental, for pointing out the obvious. I owe you one.
- Jools Wills from the RetroPie project for his custom SDL2 libraries. He saved the project!

This was originally "released" on Doom's 21st birthday, but time restraints made this release a day late. Oops!
