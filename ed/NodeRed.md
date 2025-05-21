## Node-Red Installation and Application
# Installation
1. [Download](https://nodejs.org/en/download) the proper version for your operating system.
2. Install Node-Red: Use the ```default``` settings.
3. Open Node-Red: Type ```Node-Red``` in ```Terminal``` to run it.
# Application
1. Open Node-Red ```Flow``` by visiting ```127.0.0.1:1880``` in your browser.
2. Install the ```node-red-dashboard``` module.  
![alt text](NodeRed/image.png ':size=500')  
3. Select ```mqtt in``` and ```gauge``` nodes and connect them.  
![alt text](NodeRed/image-1.png ':size=500')  
4. Set the ```mqtt in``` and ```gauge``` nodes' properties.
5. Click ```Deploy``` to deploy the flow.
6. Visit ```127.0.0.1:1880/ui``` to view the UI dashboard.  
![alt text](NodeRed/image-2.png ':size=200')