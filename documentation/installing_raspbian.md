# Installing Raspberry Pi OS #

## Easy Raspbian Setup ##

1. If you are on Windows, macOS, or Ubuntu go to [The Raspberry Pi Downloads Page](https://www.raspberrypi.org/downloads/) and download the Raspberry Pi Imager.  That downloads the latest image and writes it to your SD card.

1. Eject and re-insert the SD card

1. In explorer / finder / files, open the removable device called `boot` and create an empty file called `ssh` in the main root directory

1. create and edit a new file called `wpa_supplicant.conf` and enter the content which follows into this file

1. eject sd card and insert into raspberry pi and power it on.

1. use your router / wifi hotspot device list to find the raspberry pi and note down it's ip address.

1. Using `terminal` on Ubuntu or Mac or `putty` on Windows ssh to this ip address as user pi, and enter password `raspberry`.  Once you have logged in, change the password.

### Code for `wpa_supplicant.conf`

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<Insert 2 letter ISO 3166-1 country code here>

network={
 ssid="Name of your wireless LAN"
 psk="Password for your wireless LAN"
}
```

## Todo setup fixed IP address via CLI ##