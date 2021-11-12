# Advantech-LoRaWAN-Vibration-Temp-sensor-Solution
WISE-2410 is a LoRaWAN wireless conditional monitoring sensor integrated with ARM Cortex-M4 Processor, LoRa transceiver, 3-axis accelerometer and temperature sensor. 
Battery life cycle is 2 years with IP66 enclosure.

Brief Solution Step by Step:

If we connect WISE-2410 with our computer and the Advantech WISE Studio shows it cannot recognize the com port, then please install the driver from the following link:

https://www.advantech.com/support/details/driver?id=1-13U9QTV

Step1.
Enter the WISE 6610 gateway. Default IP: 192.168.1.1
  Account: root
  Password: root
  
<img src= "Gateway WISE-6610.png" width=800>

Step2. 
Go to user mode.

Step3. 
Click LoRaWAN Gateway to enter the setting page. Make sure all of these parameters are matching with the RF module setting on WISE-2410 Sensor.
Or click on quick setup for default setting.

Step4. 
A new tab will pop up after click on network server > enable > network > server (http)
  Account: root
  Password: root

Step5. Create an end node device according the OTAA or ABP method.
   I f select commissioned ””, which means the node will use OTAA mode for connecting with a gateway.
   I f select active nodes ””, which means the node will use ABP mode for connecting with a gateway.

Click on create in devices in activated because this project is using ABP mode for connection.

A.DevAddr: the device address of an end node.
   Copy pate from WISE-24 10 RF module tab.
B.Profile: select the model name of the WISE 6610 which used for Network Server role.
   In this demo, a EUR version is used to connect with WISE 2410NA version.
C.App Arguments: the I/O board of the end node.
   In this project, a WISE-2410 is used.
D.NwkSKey: the network service key address of an end node.
   Copy pate from WISE-2410 RF module tab.
E.AppSK ey: the application service key of an end node.
   Copy pate from WISE-2410 RF module tab.
F.Click on save to finish the setting.

Select LoRaWAN for RF operation mode setting on WISE-2410.

<img src= "Sensor WISE-2410.png" width=800>

Step6. 
Create a network server gateway. Copy paste the MAC address from LoRaWAN radio > LoRaWAN Gateway Identifier. Then click on submit.

Connection results:
1. Click application server > status. Here we will see the end nodes if packets are received by gateway from an end node.
2. The gateway will help to pre parsing the data payload if the app arguments input correctly.
3. Received frames page shows the received results. The FCnt shows the frame sequence. If this sequence is in continuously , means some of the packets were lost.

Continue with setting up:
Step7. (optional)
Connect WISE-6610 through WinSCP (FileZilla cannot connect with it). Modify the “setting.js” file of WISE 6610. So, we can insert image into dashboard. 
Put the “title.jpg” file under folder “opt/nodered /node red/” of WISE-6610. Need to reboot Node-Red service if modify the setting.js file. If we don't
want an image, we can simply delete this node. Add a line httpStatic: '/opt/nodered/node red/',

Step8.
Enable the Node-Red function on WISE-6610. Go to Customization / User Modules / Node Red webpage and enable automatic start function with the port number we prefer. 
Default port number 1880 is recommended.

Step9.
Open a new tab on a browser. Type in the IP address of the WISE-6610 and port number of the Node Red.

Step11.
Modify all of the device MAC addresses in WISE-2410 UpLink node, and Device function into the MAC of ours. Then click on deploy,

<img src= "Node-red flow.png" width=800>

Click dashboard / open. There will be the dashboard created by the program copy pasted from the notepad.

<img src= "Dashboard.png" width=800>

Visit our official website: https://polisea.ro/aiot/ 

🚩 Connect with me on social
- LinkedIn: https://www.linkedin.com/in/ariful-islam-arif-2987b51a3/
- Twitter: https://twitter.com/arifulislam301
- Instagram: https://www.instagram.com/ariful_mr_islam/

🔔 Subscribe to my YouTube channel
https://www.youtube.com/channel/UCED68cm6nHaAlAk0h9I3yAQ

