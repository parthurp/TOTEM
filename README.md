This directory contains several files that have different roles (& places in the RPi folders).

# JSON files 
They are used by Open Stage Control (presumed already installed on the Pi).
* GenVibs.json (in /home/pi/Documents/totem)

# Pure Data files
General rule is: copy whatever pd file you want (or generate your own), rename it "GenVibs.pd" and place it into RPi's directory /home/pi/Documents/totem, RPi autostart files will do the rest!
* GenVibs.pd

** In folder GenVibs_others/
* GenVibs_original_2020_12_16.pd is a backup of the PD patch that was provided as a deliverable at the end of the project TOTEM. It works! But some issues remain, such as the memory-consuming GUIs and other minor bugs.
* GenVibs_base.pd is a baseline patch that contains the minimal functions to help you build your own patch converting sound into vibration (should be improved, though, as it is very minimal)

** In folder utils/
* monitor.pd: a simple abstraction you may want to use for monitoring signals within your patch (allows to visualize the energy through env~, and the waveform on an array)


# Dependencies --- if you're starting on your own RPi without using the image we supply
* Pure Data
either use purr-data available here, 
or use pure data (install with sudo apt install puredata) and the following libraries/objects/abstractions:
- spigot~ in this repository (just leave it in the same directory as GenVibs.pd)
- [lib lyonpotpourri] for [object adsr~]: sudo apt install pd-lyonpotpourri
- [lib zexy] for [object multiplex~]: sudo apt install pd-zexy
it is possible that GenVibs.pd can't create the "multiplex~" object. In this case, just copy the file "multiplex~.pd_linux" from this repository into the same directory as GenVibs.pd
- [lib import] for [object import]: sudo apt install pd-import
- [lib mrpeach] for [object udpreceive]: sudo apt install pd-mrpeach pd-mrpeach-net
if pd has problems loading udpreceive, just open GenVibs.pd with a text editor and replace occurrences of "mrpeach/udpreceive" by "net/udpreceive"
- [lib pd-osc] for [objects routeOSC & unpackOSC]: sudo apt install pd-osc (but they should be installed with mrpeach and mrpeach-net)
if pd has problems loading routeOSC and unpackOSC, just open GenVibs.pd with a text editor and replace occurrences of "mrpeach/routeOSC" by "osc/routeOSC" and occurrences of "mrpeach/unpackOSC" by "osc/unpackOSC"
- [lib maxlib] for [object scale]: sudo apt install pd-maxlib
- [lib cyclone] for [object counter]: sudo apt install pd-cyclone
- [lib vbap] for [object vbap]: sudo apt install pd-vbap
- [lib mediasettins] for [object audiosettings]: sudo apt install pd-mediasettins
- [lib timbreID] for [objects specCentroid~ & specFlatness~]: 
git clone https://github.com/avilleret/timbreID
cd timbreID/
make
sudo make install
sudo cp -r /usr/local/lib/pd-externals/tID/ /usr/lib/puredata/extra/
