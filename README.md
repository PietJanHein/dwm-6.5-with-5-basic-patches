# dwm-6.5-with-5-basic-patches
This repository contains a minimally patched dwm 6.5. The following patches are included: systray, swallow, rotatestack, attachaside, resizecorners. 

# Instructions on how to install and setup dwm
1. Download dwm.tar and dmenu.tar and install dmenu from your repository (or rofi but then you have to change the config.h file so start with dmenu to make it easier for yourself)
2. extract dwm.tar and dmenu.tar in the terminal with "tar -xvf dwm.tar" and "tar -xvf dmenu.tar" in whatever directory you like
4. cd into the directories for dwm and tar and then run "sudo make install" and dwm and dmenu should get compiled and a binary will be made from it
5. Two options. 
First option: install xinit (on Arch the name of the package is xorg-xinit) and then copy/use the bundled xinitrc file and modify it to your liking, you probably want to change/remove the xset command in it. "cp xinitrc ~/.xinitrc" 
Second option, if you use a display manager (SDDM, GDM, LightDM): copy the file dwm.desktop to /usr/share/xsessions/  in which case you will also need to start up a few programs in ~/.Xprofile or whatever your chosen displaymanager (SSDM, GDM, LightDM) uses on your chosen Linux-distro. The first option is easier if you don't mind logging in on the tty every time when you boot the system.
6. copy the file panelfilling to wherever you like and change either .xinitrc or whatever file your displaymanager uses to start it when you start the desktopenvironment.
7. start dwm, if you use xinit then you type startx in the tty, if you use a displaymanager then you can select dwm thanks to the dwm.desktop file.

Additional tips. Use the programs lsd and bat (on Debian-based batcat) instead of ls and cat. These are superior programs and add pictograms (see the dependency to have the emoji's on your system) and syntax-highlighting (bat).  
