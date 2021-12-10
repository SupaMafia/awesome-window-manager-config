# awesomewm_config

.config file for awesome window manager.

A minimalistic window manager config. with sensible defaults and some essential functions.
Notice: use with caution. It is only tested on lubuntu 20.04 LTS. 
Could be buggy in a multiscreen setup can be buggy, but arandr helped. 
This guide assumes that you have many of the applications already such as xorg, a login manager, etc. 

#---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Dependencies: 
rofi (run launcher), dmenu(run launcher), kitty(terminal), compton, nitrogen, pasystray, nm-applet(network manager), pavucontrol (volumeicon has issue switching audio device after start), lxqt-powermanagement, xscreensaver, and dropbox (optional). Then can be installed by: 
- sudo apt update
- sudo apt full-upgrade
- sudo apt install suckless-tools kitty compton compton-conf nitrogen pasystray pavucontrol rofi xscreensaver arandr
- sudo apt install network-manager network-manager-gnome network-manager-pptp
- and the wm itself: sudo apt install awesome

Installation: 
- The config file location is at: ~/.config/awesome/rc.lua. create one if the file does not exist. 
- Replace the content of rc.lua and theme.lua. (Back up your old files first). And in rc.lua, you need to change the path of theme.lua to the file location. change this line: beautiful.init("/home/$USER_DIR$/.config/awesome/theme.lua")
- And for the best practice, put theme.lua at the same directory with rc.lua: ~/.config/awesome/. 

Run launcher:
- The default is dmenu, but you can change it to rofi by going to this line: awful.key({ modkey },            "r",     function ()
- Change the code inside " " from "dmenu_run -nb '#2f1e47' -sb '#25583a' -nf '#ffffff' -fn 'terminus-18' -b" to: "rofi -theme glue_pro_blue -show drun"
- Just by using dmenu_run or rofi -show drun works as well. the provided script adds theming. 
- If the font is too big, change the size by changing: 'terminus-18' to something like: 'terminus-10'

Autostart:
- Default uses pasystray, but you can switch to volumeicon by uncommenting the line (remove "--").

Title bars:
- By default title bars are removed. To re-enable it, change this lines: properties = { titlebars_enabled = FALSE } from FALSE to TRUE.   

Border size and panel gaps:
- In theme.lua you can change them to your liking by altering these two parameters: theme.menu_height = dpi(15) and theme.menu_width  = dpi(100)

Awesome theme colour:
- You can change it back to the default grey colour theme by using the value provided in the file.

Screensaver
- Use xscreensaver. You can configure it by xscreensaver-demo

Powermanagemwnt
- Use lxpowermanagement

Theme your applications: 
- You can use LXappearance (GTK) and qt5ct (qt).
- But you might be required to change your environment variables (for example, your can check your QT theme by: printenv QT_QPA_PLATFORMTHEME If the command returns qt5ct, the step is corret).
- Adaita-dark theme is applied in the picture. 

Other programmes you may need in a window manager:
- kvantum (more themes)
- xscreensaver (screen saver and lock screen)
- gedit/kate/vim (text editor)
- xterm (another popular terminal)
- screengrab (screenshot)
- okular (pdf)
- vlc (videos)
- fish (shell), set fish as default: chsh -s `which fish`. or set it back to default bash shell: chsh -s (which bash)
- conky (system monitor)

#---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Some potential issues and solutions while using the awesome window manager:

no wallpaper:
- nitrogen need to be launched at least once before reloading awesome

Nvidia driver causing a black screen after logging out (solved):
- solved by installing lxdm (another login manager could work as well)
- when black screen occurs, go down to tty by ctrl+alt+f1 or ctrl+alt+f2 or +f3 or + f4 .., and go back to lxdm by ctrl+alt+f7.
- Not the most elegant solution.

High DPI displays optimization:
- There are two places you can change it. First, .Xresources. Second, xorg.conf.
- check your dpi by: xdpyinfo | grep -B 2 resolution
- For nvidia user: change the xrog.conf under /etx/X11/xrog.conf by adding "option DPI" under "screen" section. Sample included. If the file does not exit, create one by: nvidia-xconfig
- Change the cursor size and dpi setting in /.Xresources. Sample included
 
Slow Rofi response
- I don't know what is the reason. but dmenu works fine.

Dropbox logo bug: white border around the logo
