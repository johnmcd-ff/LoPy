# LoPy
PYcom LoPy getting started

https://docs.pycom.io/pycom_esp32/pycom_esp32/getstarted.html

Other resources:

https://www.facebook.com/Pycom-LoPy-Triple-Network-IoT-Development-Board-985976714802190/

Our kit consists of:
2 x LoPy pcbs
2 x expansion pcbs
2 x antenna
2 x cases

Make a close inspection of the jumper connections on the expansion board.  They come lose easily and may still be in the packing.  All pins should have jumpers.

Connect the LoPy board to the expansion board.  Take note of orientation: Insert the module on the expansion board with the reset button pointing in the same direction as the USB connector.
Fit the antenna pigtail coax to the case using the lock washer and nut supplied.  It's important to connect the antenna to the LoPy to prevent damage to the RF circuit from an unmatched output. Hold the small connector carefully, line up with the pcb and push firmly.

![LoPy antenna](https://cloud.githubusercontent.com/assets/22086010/22408123/4312cc22-e6d8-11e6-88db-7b913c20b825.JPG)

![LoPy antenna close](https://cloud.githubusercontent.com/assets/22086010/22408122/430dc718-e6d8-11e6-9ef1-57e8a7c46c44.JPG)

 Note that the pigtail antenna connection has a 'flat' on it to orientate in the case.  I've also used a cable tie to hold the pigtail to the case as a strain relief.
 
 <H2>Upgrade Firmware</H2>
 
 download the upgrade tool from Pycom
 https://docs.pycom.io/pycom_esp32/pycom_esp32/getstarted.html#firmware-upgrades
 
 First use a wire to connect GND and G23 on the expansion board.  Looking at board with USB at top/Pycom logo on left:  GND is 2nd from top on right side, G23 is 4th from top on left side. 
 
![dsc_0654](https://cloud.githubusercontent.com/assets/22086010/22412195/772315d4-e710-11e6-8409-9f44748132e4.JPG)
 
 When the upgrade tool asks for the connected COM port, if you're not sure open Device Manager (windows) and check the Ports list.
 
 Follow upgrade instructions and should be done in about 1 minute.  When asked select New Zealand from the list.
 ![LoPy upgrade](https://cloud.githubusercontent.com/assets/22086010/22411604/89ab7346-e70a-11e6-9734-06827f152a09.PNG)
 Close the upgrade tool.
 Remote the jumper cable
 press the Reset button on the LoPy (next to the big LED.
 
 <H2>Start Programming</H2>
 
 Let's first check our firmware version.
 
 Start Pymakr (download from Pycom if necessary)
 Open menu:  Settings>Preferences>Pycom Device
 Ensure Device has correct Com port selected  (a username/password should not be required for a USB cable connection)
 ![Pycom settings](https://cloud.githubusercontent.com/assets/22086010/22411664/247c1448-e70b-11e6-80c7-e79555ad109d.PNG)
 
 Type these two commands:
```
import os
os.uname().release
```
The response is the latest version.  In my case 1.5.0.b2


![Pycom check](https://cloud.githubusercontent.com/assets/22086010/22411726/b910fa56-e70b-11e6-93ba-d4e401c84ca4.PNG)

### Hello LoPy
At the prompt type:
```
print("Hello LoPy")
```
Hello LoPy

<H3> Traffic Light program</H3>

Select New Program, either by
Menu>File>New
or Press button
![new program](https://cloud.githubusercontent.com/assets/22086010/22411867/4a368b8a-e70d-11e6-850e-5e41fbe99fcd.PNG)

type in following, remember indentation is important:
```
import pycom 
import time
pycom.heartbeat(False)
for cycles in range(10):
        pycom.rgbled(0x007f00)
        time.sleep(5)
        pycom.rgbled(0x7f7f00)
        time.sleep(1.5)
        pycom.rgbled(0x7f0000)
        time.sleep(4)
```
Press Run
![pycom run](https://cloud.githubusercontent.com/assets/22086010/22411901/ad694bca-e70d-11e6-8eb2-de0ad677c8c2.PNG)
The LoPy LED will start flashing.
Click in the console (Lower) window and press CTRL-C to stop
Save the program as TrafficLight

Any problems?  Press CTRL-D for a soft Reset

PYB: soft reboot

MicroPython v1.8.6-412-gf55ba50 on 2017-01-28; LoPy with ESP32

Type "help()" for more information.

