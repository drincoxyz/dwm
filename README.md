<img src=dwm.svg>

This is my fork of the [dynamic window manager](https://dwm.suckless.org), one of many [suckless](https://suckless.org) software.

## Installing

```sh
make && sudo make install && make clean
```

## st / dmenu

This build of dwm does not have the traditional shortcuts for starting [st](https://st.suckless.org) or [dmenu](https://tools.suckless.org/dmenu). A dedicated hotkey daemon ([sxhkd](https://github.com/baskerville/sxhkd) is an excellent choice) will be required to run alongside dwm.

The idea is to leave dwm-specific shortcuts to dwm - launching st and dmenu don't really fall into this category, and since not everyone uses st or dmenu, launching them shouldn't really be hardcoded into dwm.

## Shortcuts

Every shortcut is described in the man page. I try to keep it updated as much as possible.

## Patches

This build of dwm uses the following patches (in order of when they were applied, from oldest to newest):

+ [nodmenu](https://dwm.suckless.org/patches/nodmenu) - Removes the hardcoded dependency of [dmenu](https://tools.suckless.org/dmenu), another suckless software.

+ [actualfullscreen](https://dwm.suckless.org/patches/actualfullscreen) - Adds a function to toggle a window between fullscreen and windowed. Uses real fullscreen as the name would imply, as opposed to doing a combination of hiding the status bar and using the monocle layout.

+ [zoomswap](https://dwm.suckless.org/patches/zoomswap) - Changes the behaviour of zooming windows by having it swap places with the master window, as opposed to pushing the old master down the stack.

+ [restartsig](https://dwm.suckless.org/patches/restartsig) - Adds a function to restart dwm in-place, which can be done with a shortcut or by sending a signal to the dwm process.

+ [hide\_vacant\_tags](https://dwm.suckless.org/patches/hide_vacant_tags) - Tags with no windows assigned to them (vacant) are hidden from the status bar, as opposed to showing all them with a marker to indicate this state.

+ [push\_no\_master](https://dwm.suckless.org/patches/push) - Adds functions for pushing windows up or down the stack. This version doesn't affect the master window, since the zoom functionality already does this.

+ [pertag-perseltag](https://dwm.suckless.org/patches/pertag) - Gives each tag some of their own localized variables, such as the number of windows in the master stack.

+ [resetlayout](https://dwm.suckless.org/patches/resetlayout) - Resets the layout (and number of master windows) of the current tag when it has one or less windows occupying it.
