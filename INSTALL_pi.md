This file explain what should be installed on the Raspberry Pi (and how it should be installed).

# RPi working image file (for RPi 3B+)
This is the surest way of getting your system to work: cloning the image file. Just download it and put/mount it in a 16GB micro-SD card that you'll insert in your RPi. And that's it!
The image is available here:
https://yncrea-my.sharepoint.com/:u:/g/personal/arthur_pate_yncrea_fr/EWpFaAHUYxVKvHUp-UKaze4BmgSpEepBw2IumgM5pyeP2g?e=dtwjnL

# Otherwise, if you want to install the necessary files and software on another RPi configuration, here follows a list of what (and where) should be installed
* Pure Data
We've been using this version of pd, but it should work on pd vanilla.
Just do 
$ sudo apt install puredata

* Purr-Data (pd-l2ork)
We've been using this version of pd, but it should work on pd vanilla. Up to you!
"$ sudo apt install pd-l2ork" might work, otherwise go get the instructions here: http://l2ork.music.vt.edu/main/make-your-own-l2ork/software/raspberry-pi/

* Open Stage Control
Is to be installed on your RPi. Install it from here: https://openstagecontrol.ammd.net/
On our configuration (see the image file provided above), this is open stage control version 1.7.6, which is installed in /home/pi/Documents/

* Other configuration files
... conf/autostart
(to be put in /home/pi/.config/lxsession/LXDE-pi/ and in /etc/xdg/lxsession/LXDE-pi)
this file ensures pd and open stage control are launched when booting the RPi
if your PD or Open Stage Control configuration is different from ours, please change this file accordingly (paths, versions, etc.)

... conf/hotspot.txt
(to be put in /boot/)
this file configures the hotspot name and password, for connecting your smartphone to the RPi


