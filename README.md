# kodi-rc6-mce-nolirc
Files required to use most RC6 MCE remotes with Kodi and K/Ubuntu 20, without configuring LIRC.

## Supported OS/Hardware

See [Upstream Wiki](https://github.com/clontarfx/kodi-rc6-mce-nolirc/wiki/Supported-OS-Kodi-Hardware)

## Installation

* Copy rc6_mce.toml to /etc/rc_keymaps/
* Create a shell script that clears and rewrites the keymap:
``` sh
# cd ~
# mkdir ~/scripts
# cd scripts
# touch ~/scripts/initrckeymap.sh
# chmod +x ~/scripts/initrckeymap.sh
```
* Edit the shell script to contain:
``` sh
#!/bin/bash
/usr/bin/ir-keytable -c -w /etc/rc_keymaps/rc6_mce.toml
```
* Create a CronJob:
``` sh
# crontab -e
```
* Add the line near the top below the default comments:
``` sh
@reboot /bin/bash /root/scripts/initrckeymap.sh
```
* Reboot the computer:
``` sh
# reboot
```
* Double check when the OK key is pressed it shows `KEY_ENTER` with:
``` sh
$ sudo ir-keytable -t
```
* Launch Kodi.

## Why?

Because I like IR remotes as they don't need recharging every four to eight hours... plus I'm not glued to my cell.

## Quick Modify Guide

Edit /etc/rc_keymaps/rc6_mce.toml and replace the KEY_ commands with the equivalient Kodi keyboard shortcut and remember to reboot *(for now?)*.

An example would be changing KEY_BLUE to KEY_I if you wanted to make it the info key.
