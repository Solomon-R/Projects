# Setting up PiCar-B on Mac

**This is an overview on setting up the [Picar-B Mars Rover](https://www.adeept.com/adeept-mars-rover-picar-b-wifi-smart-robot-car-kit-for-raspberry-pi-4-3-model-b-b-2b-speech-recognition-opencv-target-tracking-stem-kit_p0117_s0030.html) by Adeept. Product and Licensing belongs to them.**


## Assembly

Upon getting the Picar-b kit the first thing you should notice is the lack of instructions that the car comes with for assembly. [Intructions can be found here](https://www.youtube.com/watch?v=rej4IVRftw0&list=PL_4i_XWwRYF8btqCxPPAe39CTEdKnOouk&index=2) for assembly of the car. 

### Servo Calibration
There are some confusing parts within the video that appear though. The first would be the calibration of the servos. When mentioning this they just look like they are twisting the servo back and forth to see if they are operational. There is a purpose to this though. What you are trying to do is to make sure that the servo can twist 90 degrees in either direction so that when you do finally plug the servo into the adeept shield and start up the car for the first time you don't have to go back and unscrew certain parts to align the servos correctly. Doing so can save the hastle and stress of taking apart the car and fustratingly putting it back together out of reccomended order. An example of a righfully calibrated servo is the one found that controlls steering of the car. When this is done correctly the wheels should be able to turn left and right without any resistance. If the turning is restricted on one side and goes too far on the other your servo is not calibrated correctly.

### Gentleness
Another not fully explained part of the tutorial is the gentleness required when screwing on the ultrasonic sensor and the camera. Both of these sensors have their chips facing the surface that the sensor is getting screwed on to. This means that if screwed on too tight you might damage the chip. To avoid this make sure that you are not screwing the sensors on too tight to the surface.

### Wiring
The video says to refer to the manual. The manual can be found on the page of the Picar itself. Ignore the motor 2 port.

## Software

The [original video](https://www.youtube.com/watch?v=BABIi4LhFlM&list=PL_4i_XWwRYF8btqCxPPAe39CTEdKnOouk&index=1) for software installation.

### Micro-SD for Raspberry-Pi OS
The video is directed for Windows users and as such tells you everything you need to do for Windows. The video says to use win32 disk imager to flash the os onto the micro sd card. For mac you can use [balenaEtcher](https://www.balena.io/etcher/). The program is extremely straightforward to use, just choose the file you want to flash onto the micro-sd and it handles the rest.

#### **This is a disclaimer for setting up the proper software on the computer. If you are able to access the raspberry pi with a monitor, keyboard, and mouse, do it. If this is the case you do not need the computer at all as you are able to write the code directly on the raspberry pi instead of relying on using ssh to connect to the raspberry pi.**

### Setting up software on your mac
This is for people who do not have a spare keyboard, mouse, and monitor lying around and instead will be using their computer to connect to the raspberry pi. Even if you can only access the raspberry pi through your computer you still do not need to download all the python packs that the video asks you to do on your computer as the inital set up that is asked through the video of the raspberry pi has all the packs included onto the raspberry pi. 

#### Connecting to Raspberry pi via ssh
To connect to the raspberry pi's terminal via ssh, you need enable ssh on your raspberry pi. You can do so in the reaspberry pi settings menu if you have access to a mouse, keyboard, and monitor. But you wouldn't be doing this anyways if you could. Another way to enable it is creating an empty file inside the micro sd before booting up the rasberry pi with the micro sd card. To do so on mac you can go to the micro sd directory within terminal and use the command `$ touch ssh`. You also want to make the wpa_supplicant file that it asks you to make in the video to enable wifi on the raspberry pi once again using the command `$ touch wpa_supplicant.conf` and following what they ask you to type onto the file. From here you want to find the ip address of the raspberry pi. You can do this using your router and finding a list of the ip addresses using your wifi. You are now able to remotely connect to your raspberry pi using your mac. 

You can connect via ssh by pressing command k or by being within the desktop of the mac and pressing the go drop down menu found in the upper left hand corner of your monitor and clicking on Connect to Server. Within in the menu type `ssh://pi@(IP address of pi)` into the bar and press connect. This should bring you to terminal and prompt you with "Are you sure you want to connect?" prompt. Just type `yes`. You will then be prompted with the raspberry pi password. If you haven't altered the password, the default password is raspberry. When giving commands to the raspberry pi make sure that the pi is on.

#### Connecting to Raspberry pi via VNC
You can connect to the raspberry pi remotely through a VNC server. This will allow you to use the raspbery pi as a remote desktop on your computer. [This video directs you on how to set up a VNC server and connect to it](https://www.youtube.com/watch?v=Oj_6SMktlso).

#### Setting up Raspberry pi for picar use
Once connected to the raspberry pi through ssh follow the directions that the video asks you to do within putty. The second prompt they ask you to download under the #adeept_picar-b/server# directory was not downloadable; this is because setup.py was not found in the server directory as instructed and can instead be found under #adeept_picar-b# direcory. Instead

But if you are going to write the code on you computer and transfer it to the raspberry pi you still need 
