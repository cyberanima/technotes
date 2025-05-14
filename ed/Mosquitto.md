## Mosquitto Broker Installation and Configuration
1. Download [Mosquitto Broker](https://mosquitto.org/download/):  

![alt text](Mosquitto/image-3.png ':size=500')  
2. Installation: Use the ```default``` settings.  
3. Open the ```mosquitto.conf``` file in the ```mosquitto``` folder and add the following lines: (Remember to ```save``` it.)
```conf
allow_anonymous true
listener 1883 0.0.0.0
```
![alt text](Mosquitto/image-4.png ':size=500')  
4. Run ```Service``` to Start (if Stopped) or ```Restart``` the Mosquitto Broker.  
![alt text](Mosquitto/image-5.png ':size=500')  
![alt text](Mosquitto/image-6.png ':size=500')  
5. Run ```Windows Defender Firewall with Advanced Security``` and add the new MQTT rule:   
![alt text](Mosquitto/image-7.png ':size=500')  
![alt text](Mosquitto/image-8.png ':size=500')  
![alt text](Mosquitto/image-9.png ':size=500')  
![alt text](Mosquitto/image-10.png ':size=500')  
![alt text](Mosquitto/image-11.png ':size=500')  
![alt text](Mosquitto/image-12.png ':size=500')  
![alt text](Mosquitto/image-13.png ':size=500')  
6. Run MQTTX and MQTTool/MyMQTT to test the Mosquitto Broker.