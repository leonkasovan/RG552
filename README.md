# RG552
Knowledge for Handheld Anbernic Device RG552  
https://retrogamecorps.com/2021/12/27/anbernic-rg552-linux-setup-guide/  
https://retrogamecorps.com/2022/08/16/anbernic-rg552-epic-retro-gaming-guide/ 
https://retrogamecorps.com/2022/04/07/anbernic-rg552-custom-firmware-guide/  
https://retrogamecorps.com/2022/07/13/amberelec-setup-and-update-guide/  

## Stock (LINUX and Android) firmware:  
https://rs97.bitgala.xyz/RG552/  

Preconfiguration script in LINUX  
Open ssh IP ADDRESS (192.168.1.X) and execute this command:
`wget https://raw.githubusercontent.com/konsumschaf/settings.sh/main/settings.sh -O - | /bin/bash`


## Install LINUX custom firmware:   
1. Batocera.linux: https://batocera.org/download  
2. AmberElec https://amberelec.org/download  
3. JELOS: https://github.com/JustEnoughLinuxOS/distribution/releases/latest(must use 64Gb SDCard!)  
Flash it with Rufus 

## Download and install BIOS for emulators in Batocera v37  
http://theminicaketv.free.fr/bios.html  
PGM https://www.planetemu.net/rom/fb-alpha/pgm-2 put pgm.zip to /userdata/roms/fbneo  

## Enable local terminal in device  
Edit /etc/inittab
```
S0::respawn:/sbin/getty -n -L -l /usr/bin/batocera-autologin console 115200 vt100 # GENERIC_SERIAL
2:3:respawn:/sbin/getty 38400 tty2 -a root
3:3:respawn:/sbin/getty 38400 tty3 -n -l /usr/bin/mc
4:3:respawn:/sbin/getty 38400 tty4 -n -l /usr/bin/batocera-mixer
# 5:3:respawn:/sbin/getty 38400 tty5 -n -l /bin/bash #it's working but press 3 button simulanously
```
