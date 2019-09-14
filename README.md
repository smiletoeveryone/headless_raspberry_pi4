# headless_raspberry_pi4
![](https://github.com/smiletoeveryone/headless_raspberry_pi4/blob/master/raspbian%20os%20installation%20tutorial%20without%20a%20monitor.bmp)
![](https://fsmedia.imgix.net/27/5c/ab/c8/5ec4/4f97/b446/193294a8cb0a/raspberry-pi-4.png?#rect=0%2C84%2C1600%2C803&auto=format%2Ccompress&w=650)

Hopefully, you are able to install the os for your raspberry pi without a monitor after reading this toturtial.
You would read 3 topics in the tutorial.
1. introduction to raspberry pi4 / pi3
2. raspbian os installation withput a monitor
3. more information

you are able to input the command "pinout" in the terminal of your raspberry pi4 as well, you would get gpio information as below:
![](https://github.com/smiletoeveryone/headless_raspberry_pi4/blob/master/rpi4_pinout.jpg)

installation steps:

1.format your sd card as fat32 under ms windows.

2.download raspbian os. https://www.raspberrypi.org/downloads/raspbian/

3.download balenaetcher and install it for flashing the os image into sd card. https://www.balena.io/etcher

4.creat a ssh file without extension for turnung on ssh in the boot area of sd card.

5.creat a wpa_supplicant.conf as well in the same area as ssh file for connecting to the wifi.
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="NETWORK-NAME"
    psk="NETWORK-PASSWORD"
}

6.finishing above steps, place the sd card in your raspberry pi3/4 and reboot/power on it.

7.try to get the ip address of your raspberry pi3/pi4 in the wifi router.

8.:/sudo ssh pi@192.168.XXX.XXX
default password:raspberry
******
   if you got an error message as "Hot key verification failed", input the command as below in the terminal.
ssh-keygen -R 192.168.xxx.xxx
******s

9.:/sudo raspi-config, get into the menu for turning vnc on thet you would be able to control  your raspberry pi3/p4 remotely.

10. install vnc viewer and server.  
sudo apt-get update
sudo apt-get install realvnc-vnc-server realvnc-vnc-viewer

11.install vnc viewer for your ms windows. 

12.get into the setup menu again for booting into the graphic desktop later, meanwhile try to adjust a correct screen revolution.

sudo raspi-congfig

******
Do 'sudo apt-get install lightdm' to allow configuration of boot to desktop
******

13.turn on vnc and ssh in the interface option.

14.return to the main menu of raspi-config.

15.enter "3. boot options" for choosing "B1 Desktop/CLI".

16.then enter "B3 Desktop" or Desktop Autogin" what you like.

17. do not forget to save your setup after all.

18.then reboot your raspberry_pi.

19.run vnc viewer on you ms windows and connect your raspberry_pi by network IP what you got earlier. 

20.it is all done for installing the os.
