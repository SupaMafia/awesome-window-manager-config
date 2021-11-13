# awsomewm .config

.config file for awesome window manager.

A minimalistic window manager config. with only essential functions.
It is only tested on lubuntu 20.04 LTS. Notice: use with caution.

The config file loaction is at: ~/.config/awesome/rc.lua. create one if the file does not exist. 

Dependencies: rofi, dmenu, kitty(terminal), compton, nitrogen, pasystray, nm-applet(network manager), pavucontrol (volumeicon has issue switching audio device after start), and dropbox (optional).
- install by: 
- sudo apt update
- sudo apt upgrade
- sudo apt install suckless-tools kitty compton compton-conf nitrogen pasystray pavucontrol rofi
- sudo apt install network-manager network-manager-gnome network-manager-pptp
- and the wm itself sudo apt install awesome

Installation: in rc.lua, you need you change the path of theme.lua to the file location. change this line: beautiful.init("/home/$USER_DIR$/.config/awesome/theme.lua")

Some potential issues and solutions while using the awesome window manager:

nvidia driver casuing a black screen after log out (solved):
- solved by installing lxdm (other login manager could work as well)
- when black screen occurs, go down to tty by ctrl+alt+f1 or ctrl+alt+f1 or ctrl+alt+f2 or +f3 or + f4, and go back to lxdm by ctrl+alt+f7.

for High DPI displays optimization:
- check your dpi by: xdpyinfo | grep -B 2 resolution
- for nvidia: change the xrog.conf under /etx/X11/xrog.conf by adding "option DPI" under "screen" section. Sample included
- if the file does not exit, create one by nvidia-xconfig
- or change cursor size and dpi setting in /.Xresources. Sample included

theme your applications: 
- use LXappearance (GTK) and qt5ct (qt)
- you may need to check (ex. printenv QT_QPA_PLATFORMTHEME) or fix your environment variable 
