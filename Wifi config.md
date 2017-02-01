##Connect direct to LoPy via built-in wifi hotspot

When LoPy first turns on, it provides a wifi access point you can connect directly to.  This allows Telnet and FTP instead of USB.

https://docs.pycom.io/pycom_esp32/pycom_esp32/getstarted.html#initial-configuration

Connect your computer to the WiFi network named after your board (e.g. lopy-wlan-xxxx, wipy-wlan-xxxx). The password is www.pycom.io
Open Pymakr.
In the menu, go to Settings > Preferences (Pymakr > Preferences on macOS).
In the left list look for Pycom Device.
For device, type down 192.168.4.1. The default username and password are micro and python, respectively.
Click OK

![pycom wifi](https://cloud.githubusercontent.com/assets/22086010/22412362/9005d5c6-e712-11e6-8a0d-4eba5e228e58.PNG)

If you want to use Telnet or FTP use the same settings.  There are some important notes to follow:  Ensure FTP is plain/insecure.  Use Passive transfer mode with maximum of 1 connection.  Detail of this is in link above.

##  Setup LoPy to your wifi network

Next we'll connect to a local wifi network.
