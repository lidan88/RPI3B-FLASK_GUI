# tankcontroller
Water Tank Controller Project using RPI 3B and Kisosk + Flask



Instruction manual for 
RPI Tank Controller





Contents
Wiring diagram	2
Prerequisite	2
Install wifi library package	3
Enable SPI interface on RPI	4
Install Tank controller program	7
Install python Flask and configure auto start	8
Configure auto start of python source	9
Install Adafruit GPIO library	10
Install Adafruit MAX31885 library	10
Configure as Kiosk mode	10




 


Wiring diagram

 

Prerequisite

First, we have to install Raspbian Jessie on RPI 3B.
If you don’t have Raspbian Jessie image not Raspbian Stretch, I can send you.

And then we have to enable SSH on RPI3B.
There are several ways to enable ssh on rapbian.
Because, we are using 7” TFT touch LCD, you can configure on Touch LCD.
 

And then, you have to get IP address of RPI. In my testing, ip address is 192.168.1.140.
 

Reboot RPI.

Install wifi library package

Connect to RPI using putty
I am using putty on windows.

 



In terminal(putty), we have to enter “sudo pip install wifi” command.

 

Enable SPI interface on RPI
 
sudo raspi-config


 

 
 


 

 

 

 

Reboot again.

Install Tank controller program

I can deploy this on my git repo, so that, you can install from my git.
After we have completed milestone1, I will deploy it on git.

Now, we will test using source.
Using SCP or another FTP client, we can install source on RPI.
I am using WinSCP.


 

Copy tankController directory into /home/pi directory on RPI.

Install python Flask and configure auto start
Connect to RPI using putty again.
And then, enter “sudo pip install python Flask”.
 

Configure auto start of python source
In putty terminal, enter sudo nano /etc/rc.local
 

Before “exit 0”, add following commands.
 

 sudo python /home/pi/tankController/tankController.py
Save it to press Ctrl + O.
Exit form that to press Ctrl + X.
Install Adafruit GPIO library
In terminal, we have to enter following commands
git clone https://github.com/adafruit/Adafruit_Python_GPIO.git
cd Adafruit_Python_GPIO
sudo python setup.py install

Install Adafruit MAX31885 library
git clone https://github.com/adafruit/Adafruit_Python_MAX31855.git
cd Adafruit_Python_MAX31855/
sudo python setup.py install

Configure as Kiosk mode
So that program will auto run with full screen, when rpi boots.
sudo nano /home/pi/.config/lxsession/LXDE-pi/autostart

 


Edit as follows and save it.
 
Exit and reboot.

So, program will start automatically when RPI boots.

Gui will be displayed on your RPI, backend for control logic will be performed.
