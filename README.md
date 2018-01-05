# kodi-rc6-mce-nolirc
Files required to use most RC6 MCE remotes with Kodi and Ubuntu 17, without LIRC.

## Supported OS/Hardware

See [Wiki](https://github.com/clontarfx/kodi-rc6-mce-nolirc/wiki/Supported-OS-Kodi-Hardware)

## DO NOT INSTALL LIRC, IT IS NOT REQUIRED FOR THIS TO WORK CORRECTLY.

`apt-get remove *lirc* --purge`

Also get rid of any keymap files you have in your user's .kodi directory. They aren't required.

## Installation

1. Copy rc6_mce to /etc/rc_keymaps/
2. Restart and reload the rc keymap
. `sudo ir-keytable -c -w /etc/rc_keymaps/rc6_mce`
3. Restart Kodi

## Why?

Because I couldn't be fucked fucking around with trying to get LIRC and Kodi and devinput working with Ubuntu 17.

## Quick Modify Guide

Edit /etc/rc_keymaps/rc6_mce and replace the KEY_ commands with the equivalient Kodi keyboard shortcut.

An example would be changing KEY_BLUE to KEY_I if you wanted to make it the info key.