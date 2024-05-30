# dwm-6.5-with-5-basic-patches
This repository contains a minimally patched dwm 6.5. The following patches are included: systray, swallow, rotatestack, attachaside, resizecorners. 

# Instructions on how to install and setup dwm
1. Download dwm.tar and dmenu.tar and install dmenu from your repository (or rofi but then you have to change the config.h file so start with dmenu to make it easier for yourself)
2. Extract dwm.tar and dmenu.tar in the terminal with "tar -xvf dwm.tar" and "tar -xvf dmenu.tar" in whatever directory you like
3. cd into the directories for dwm and tar and then run "sudo make install" and dwm and dmenu should get compiled and a binary will be made from it
4. Two options. 
First option: install xinit (on Arch the name of the package is xorg-xinit) and then copy/use the bundled xinitrc file and modify it to your liking, you probably want to change/remove the xset command in it. "cp xinitrc ~/.xinitrc" 
Second option, if you use a display manager (SDDM, GDM, LightDM): copy the file dwm.desktop to /usr/share/xsessions/  in which case you will also need to start up a few programs in ~/.Xprofile or whatever your chosen displaymanager (SSDM, GDM, LightDM) uses on your chosen Linux-distro. The first option is easier if you don't mind logging in on the tty every time when you boot the system.
5. copy the file panelfilling to wherever you like and change either .xinitrc or whatever file your displaymanager uses to start it when you start the desktopenvironment.
6. start dwm, if you use xinit then you type startx in the tty, if you use a displaymanager then you can select dwm thanks to the dwm.desktop file.
7. If you want to change the hotkeys, the number of workspaces or anything else then open the config.h file in your dwm-directory, make those changes and run "sudo make install" again, if you made a mistake then you will keep the last succesfully compiled version of dwm (the binary only changes after succesful compilation but of course you should always make a backup before changing any file in your dwm-directory.You can for example remove workspaces by removing those from the array in which they got defined and used. It is explained in the config-file, first you name all the workspaces, further down in the config-file you define hotkeys for the workspaces.
8. If you want to add or remove patches. You can find the used patches in the diff-directory which I included in the dwm.tar, yo8u can find new patches on https://dwm.suckless.org/patches/ 
You can try automated patching by using the patch program on your system (type "man patch" to see it confirmed that you have it and to read the instructions), by simply having the diff-file in the dwm-directory you can patch it by typing "patch < diffile", but you will have to manually fix it because after a number of patches the patch-program gets confused. If you want to patch manually then simply open the diff-file in any text-editor which uses syntax-highlighting (that makes it much easier!) and figure out the structure of the patchfile: it tells which files get changed, which lines to add, which lines to remove and where you can fine those lines (line-number and columnn). Figure out the logic of the dwm.c and config.h file. For example, if you are not sure where to add a part in the c-file but you can tell that you add a function and you see that all the functions are on the bottom of the dwm.c file then it is pretty easy to figure out where you should add it. There are videos on YouTube which show the process, it is not difficult if you take the time to follow it. 

Additional tips. Use the programs lsd and bat (on Debian-based batcat) instead of ls and cat. These are superior programs and add pictograms (see the dependency to have the emoji's on your system) and syntax-highlighting (bat).  
