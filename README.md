# GamingTable

As part of TEJ4M1, [Collin Town](https://github.com/towner-10) and I worked on making a gaming table. The purpose of this repository is to document our progress.
We were interrupted by a stay-at-home order during the pandemic, so we were unable to complete the physical gaming table.


The gaming table would have used GPIO buttons and analog inputs to control games run on a Raspberry Pi running Retropie. As well, we would have had several self-made games, such as the [reaction time game](tbd).


## Parts:
- [RetroPie Setup](#setup)
- [GPIO To EmulationStation Input](https://github.com/Dart513/GamingTable/blob/main/controls/CONTROLS.md)
- [Table Design](tbd)
- [PCB](https://github.com/Dart513/GamingTable/blob/main/pcb/PCB.md)
- [Reaction Time Game](tbd)


<a name="setup" />
### Raspberry Pi With Retropie, Desktop & EmulationStation

A guide to basic RPi setup

### Installation:
Using a computer capable of running a disk imaging software, follow the *Installation* portion of this guide online.
https://retropie.org.uk/docs/First-Installation/

### Setup:

#### Wireless:
On the freshly flashed micro SD card, insert a file called `wpa_supplicant.conf` into the boot volume.
Fill it out with the necessary information in this format:
 ```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<Insert 2 letter ISO 3166-1 country code here>

network={
 ssid="<Name of your wireless LAN>"
 psk="<Password for your wireless LAN>"
 id_str="<Some ID to distinguish this network from any others you may put into wpa_supplicant.conf>"
}
``` 
 
 <br>
 
 #### SSH
 Enable SSH from the get-go by placing an empty file called `SSH` into the boot volume. Easy.

#### First-Time Setup
Hook up the Raspberry Pi to a monitor and keyboard or controller. Plug in the Raspberry Pi, and go through the first-time setup of the control scheme. 

In the first-time setup script, find the main menu option listed as `Configuration / Tools >> Raspbiantools >> Install Pixel Desktop Environment`. Disable the screen blanker, enable needed kernel modules, and upgrade Raspbian packages.


Restart, and you should find the desktop environment available in Ports. As well, in the Retropie config menu, you should find the `RASPI-CONFIG` option, which will let you turn on VNC and I2C.

