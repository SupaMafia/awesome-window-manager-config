# awsomewm .config

*Not finished* .config file for awesome window manager, will be updated

file loaction: /.config/awesome/rc.lua  

if the file do not exit, create one.

Dependencies: dmenu, kitty(terminal), compton, nitrogen, volumeicon, nm-applet(network manager), pavucontrol (volumeicon has issue switching audio device after start), and dropbox.   

for nvidia driver casuing a black screen after log out (solved):
- solved by removeing sddm, and install lxdm
- when black screen occurs, go back to tty by ctrl+alt+f5 and go back to GUI: lxdm by ctrl+alt+f7.

for High DPI displays:
- check your dpi by: xdpyinfo | grep -B 2 resolution
- for nvidia: change the xrog.conf under /etx/X11/xrog.conf by adding "option" under "screen" section. Sample included
- or change cursor size and dpi setting in /.Xresources. Sample included
