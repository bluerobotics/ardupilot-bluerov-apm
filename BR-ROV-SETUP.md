ROV Setup
=========

This branch includes minor modifications to the APMRover2 code to allow control of an ROV or other vehicle through ROS.

#Mac Compilation Environment 

```bash
git clone -b br-ros-rov http://github.com/bluerobotics/ArduPilot
cd ArduPilot/APMrover2/
make configure
cd ..
vim config.mk
```

At this point you may have to modify the setting in config.mk. I had to point it to my Arduino installation and change the serial port. Arduino 1.0 or greater is required.

```bash
cd APMrover2
make
make upload
```

#MAV Proxy to Test

MAV Proxy lets you send messages to the APM including the set servo message.

```bash
sudo pip install MAVProxy
mavproxy.py --master=/dev/tty.usbxxxxx
```

Once started, you can set the servo with the following command:

```bash
servo set [servo num] [microsecond signal]
```