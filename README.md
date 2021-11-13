# awsomewm .config

*Not finished* .config file for awesome window manager, will be updated

minimalistic window manager config

file loaction is at: /.config/awesome/rc.lua. create one if the file does not exist. 

Dependencies: dmenu, kitty(terminal), compton, nitrogen, pasystray, nm-applet(network manager), pavucontrol (volumeicon has issue switching audio device after start), and dropbox (optional).
- install by: 
- sudo apt update
- sudo apt upgrade
- sudo apt install suckless-tools kitty compton compton-conf nitrogen pasystray pavucontrol rofi
- sudo apt install network-manager network-manager-gnome network-manager-pptp

Installation: in rc.lua, you need you change the path of theme.lua to the file location. change this line: beautiful.init("/home/$USER_DIR$/.config/awesome/theme.lua")

Issues and solutions when using the awesome window manager

for nvidia driver casuing a black screen after log out (solved):
- solved by installing lxdm (other login manager could work as well)
- when black screen occurs, go down to tty by ctrl+alt+f1 or ctrl+alt+f1 or ctrl+alt+f2 or +f3 or + f4, and go back to lxdm by ctrl+alt+f7.

for High DPI displays:
- check your dpi by: xdpyinfo | grep -B 2 resolution
- for nvidia: change the xrog.conf under /etx/X11/xrog.conf by adding "option DPI" under "screen" section. Sample included
- if the file does not exit, create one by nvidia-xconfig
- or change cursor size and dpi setting in /.Xresources. Sample included

to theme your applications 
- use LXappearance (GTK) and qt5ct (qt)
- you may need to check (ex. printenv QT_QPA_PLATFORMTHEME) or fix your environment variable 
