# awsomewm .config

.config file for awesome window manager.

A minimalistic window manager config. with only essential functions.
Notice: use with caution. It is only tested on lubuntu 20.04 LTS. And multiscreen stepup could be buggy. 
This guide assumes that you have many of the applications already such as xorg, a login manager and etc. 

#---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Dependencies: rofi (run launcher), dmenu(run launcher), kitty(terminal), compton, nitrogen, pasystray, nm-applet(network manager), pavucontrol (volumeicon has issue switching audio device after start), and dropbox (optional). Then can be installed by: 
- sudo apt update
- sudo apt full-upgrade
- sudo apt install suckless-tools kitty compton compton-conf nitrogen pasystray pavucontrol rofi
- sudo apt install network-manager network-manager-gnome network-manager-pptp
- and the wm itself: sudo apt install awesome

Installation: 
- The config file loaction is at: ~/.config/awesome/rc.lua. create one if the file does not exist. 
- Replace content of rc.lua and theme.lua. (Backup your old file first). And in rc.lua, you need to change the path of theme.lua to the file location. change this line: beautiful.init("/home/$USER_DIR$/.config/awesome/theme.lua")
- And for the best practice, put theme.lua needs at the same directory with rc.lua: ~/.config/awesome/. 

Theme your applications: 
- use LXappearance (GTK) and qt5ct (qt)
- you may need to change your environment variables (for example, checking your QT theme by: printenv QT_QPA_PLATFORMTHEME)
- Adaita-dark applied in the picture 

Other programmes you may need in a window manager:
- kvantum (more themes)
- xscreensaver (screen saver and lock screen)
- gedit/kate/vim (text editor)
- xterm (another popular terminal)
- screengrab (screenshot)
- okular (pdf)
- vlc (videos)

#---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Some potential issues and solutions while using the awesome window manager:

no wallpaper:
- nitrogen need to be launched for at least once before reloading awesome

nvidia driver casuing a black screen after log out (solved):
- solved by installing lxdm (other login manager could work as well)
- when black screen occurs, go down to tty by ctrl+alt+f1 or ctrl+alt+f2 or +f3 or + f4 .., and go back to lxdm by ctrl+alt+f7.

for High DPI displays optimization:
- check your dpi by: xdpyinfo | grep -B 2 resolution
- for nvidia: change the xrog.conf under /etx/X11/xrog.conf by adding "option DPI" under "screen" section. Sample included
- if the file does not exit, create one by nvidia-xconfig
- or change cursor size and dpi setting in /.Xresources. Sample included
- 
slow Rofi response
- I don't know what is the reason. but dmenu works fine.
