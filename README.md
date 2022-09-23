# IoT-Light-Anomoly-Detection-System

The project that I have created is used to detect anomaly in the regular light with the help of LDR sensor which is light dependent register. 
LDR is used to get value of the intensity of light. The data is collected from LDR and send to the bolt cloud using bolt WIFI module. 
The data is analyzed by using z-score. If any anomaly found, then the system will play a buzzer and send SMS to my mobile. 
The vidio link of this project is https://youtu.be/qP5azCur8Fs .

This project can be used in security system. Let’s take an example of a diamond kept in some regular light. If some person try to steal it, 
then the LDR attached to it sense the anomaly, the system will play buzzer and send SMS to police.

# Things used in this project
## Hardware components

Assorted Connecting Wires : 4 Assorted Connecting Wires are used to connect Bolt Wi-Fi module to Breadboard.
Bolt Wi-Fi module : It is used to send data to cloud and receive data from cloud.
LDR : It is used to detect the intensity of light.
Resistor : It is used with LDR.
Buzzer : It is used to alert when any anomaly is detected in light.
Breadboard : It is used to make the circuit connection easy.

# Software, Apps and online services
These are the Software, Apps, and online services that you need in this project

Setting up VMware Workstation with Ubuntu server : To setup the VMware download two software from given links: 
VirtualBox – https://www.virtualbox.org/wiki/Downloads 
Ubuntu Server ISO link – http://releases.ubuntu.com/16.04/ubuntu-16.04.6-server-i386.iso 
You can follow steps from YouTube video https://youtu.be/ubdcqfNSpkQ
Getting the API key and Device ID of the Bolt Wi-Fi module : 
After creating an account on the Bolt Cloud, you can access your API key and Device ID from the API tab and the Devices tab respectively of your Bolt Cloud dashboard.
Setting up the Bolt Python library: 
Before you proceed to this step, first ssh(login) to your Ubuntu server and follow the below steps to use Bolt Python library in your code.

Step 1: Update the packages on Ubuntu

Execute the command below so that the packages on Ubuntu are updated to the latest version. If you skip this step, you may encounter an error 
while installing the Boltiot package.

sudo apt-get -y update

Step 2: Install python3 pip3

pip3 is a package manager for python3 used to install and manage packages and python libraries. It is system independent.

Install pip3 using the following command,

sudo apt install python3-pip

Step 3: Installing boltiot library using pip

Now we will install the boltiot python library on your Ubuntu server.

Type the below command in terminal to install boltiot python library.

sudo pip3 install boltiot

Creating an account on Twilio : Twilio is a third-party SMS functionality provider. It is a cloud communications platform as a service (PaaS) company. 
Twilio allows software developers to programmatically make and receive phone calls and also send and receive text messages using its web service APIs.
You can create an account on Twilio by following this video: https://youtu.be/ASmCvopXy_A

# Hardware setup

Step1 : Connect an assorted connecting Wire from GND of Bolt Wi-Fi Module to Breadboard. (Assume its color as white)

Step2 : Connect an assorted connecting Wire from pin 0 of Bolt Wi-Fi Module to Breadboard. (Assume it is black)

Step3 : Connect Buzzer to Breadboard such that its longer leg connected to Black wire and shorter leg to white wire.

Step4 : Connect an assorted connecting Wire from A0 of Bolt Wi-Fi Module to Breadboard. (Assume its color as gray)

Step5 : Connect an assorted connecting Wire from 3V3 of Bolt Wi-Fi Module to Breadboard. (Assume its color as red)

Step6 : Connect one end of LDR to gray wire and other end to red wire via Breadboard

Step7 : Connect one end of resistor to red wire and other end to white wire via Breadboard.

conf.py file used to store the credentials of Different API used in our Project

The anomaly_detection.py file will contain the main code. The algorithm for the code can be broken down into the following steps:

1) Fetch the latest sensor value from the Bolt device.

2) Store the sensor value in a list, that will be used for computing z-score.

3) Compute the z-score and upper and lower threshold bounds for normal and anomalous readings.

4) Check if the sensor reading is within the range for normal readings.

5) If it is not in range, send the SMS and play buzzer.

6) Wait for 10 seconds.

7) Repeat from step 1.
