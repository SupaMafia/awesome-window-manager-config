# awsomewm .config

*Not finished* .config file for awesome window manager, will be updated

minimalistic window manager config

file loaction is at: /.config/awesome/rc.lua. create one if the file does not exist. 

Dependencies: dmenu, kitty(terminal), compton, nitrogen, volumeicon, nm-applet(network manager), pavucontrol (volumeicon has issue switching audio device after start), and dropbox.

Issues and solutions when using the awesome window manager

for nvidia driver casuing a black screen after log out (solved):
- solved by removeing sddm, and install lxdm
- when black screen occurs, go back to tty by ctrl+alt+f5 and go back to GUI: lxdm by ctrl+alt+f7.

for High DPI displays:
- check your dpi by: xdpyinfo | grep -B 2 resolution
- for nvidia: change the xrog.conf under /etx/X11/xrog.conf by adding "option DPI" under "screen" section. Sample included
- or change cursor size and dpi setting in /.Xresources. Sample included
