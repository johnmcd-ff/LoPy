##Connect direct to LoPy via built-in wifi hotspot

When LoPy first turns on, it provides a wifi access point you can connect directly to.  This allows Telnet and FTP instead of USB.

https://docs.pycom.io/pycom_esp32/pycom_esp32/getstarted.html#initial-configuration

Connect your computer to the WiFi network named after your board (e.g. lopy-wlan-xxxx, wipy-wlan-xxxx). The password is www.pycom.io
Open Pymakr.
In the menu, go to Settings > Preferences (Pymakr > Preferences on macOS).
In the left list look for Pycom Device.
For device, type down 192.168.4.1. The default username and password are micro and python, respectively.
Click OK

![pycom wifi2](https://cloud.githubusercontent.com/assets/22086010/22530879/b706cbd0-e942-11e6-834b-07a59a1a17ff.png)

If you want to use Telnet or FTP use the same settings.  There are some important notes to follow:  Ensure FTP is plain/insecure.  Use Passive transfer mode with maximum of 1 connection.  Detail of this is in link above.  We don't need to use a terminal connection, this is only a demonstration.  Pymakr can do all we need.

##  Setup LoPy to your wifi network

Next we'll connect to a local wifi network.

![pycom wifi0](https://cloud.githubusercontent.com/assets/22086010/22532084/ef50f298-e949-11e6-826c-83ce3dd58db8.png)

use the SSID wifi network name and password for your local network.
The command WLAN().ifconfig() informs us of the IP address that has been set.  It is also possible to set a fixed IP if required, using:  WLAN().ifconfig(config=('IP', 'netmask', 'gatewayIP', 'DNS'))

## Setting wifi from boot

Now we'd like to put the wifi setup in the boot.

First let's make a file to store the commands.  In Pymakr, start a New Project, called homewifi.
Create a new file:  homewifi.py

![pycom wifi3](https://cloud.githubusercontent.com/assets/22086010/23890352/5aa2118c-08f6-11e7-874f-ce5f270949cc.png)

Save the file, this file can be run  ![pycom run](https://cloud.githubusercontent.com/assets/22086010/22411901/ad694bca-e70d-11e6-8eb2-de0ad677c8c2.PNG)

We want to call homewifi.py from main.py, so edit this file to add the line:
![pycom wifi4](https://cloud.githubusercontent.com/assets/22086010/22532613/243c9bf8-e94d-11e6-8c33-2c6bdefcff9a.png)

then Sync the project using the button  ![pycom sync](https://cloud.githubusercontent.com/assets/22086010/22532452/046d398c-e94c-11e6-9d42-430064f33c67.PNG)

I've had to copy the new main.py to LoPy using Filezilla.  How can Pymakr replace the correct file in /flash ?

Press CTRL-D for a soft reset to run the code.  It will also be saved and run after power up.

![pycom wifi](https://cloud.githubusercontent.com/assets/22086010/22529345/fa263920-e93b-11e6-9d96-b82c8daa90fa.png)
