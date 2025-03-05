# Why you can't use D2 in WOKWI?

In today's lesson, we learnt how to use the ESP32-DevKitC to blink an LED. The LED is connected to D2. However, in WOKWI, some students found that they can't use D2 to blink the LED. This is a library bug in WOKWI.  

When you use the starter template, it works fine.  
![alt text](image.png ' :size=x250')![alt text](image-1.png ' :size=x250')

But when you create a new project, it doesn't work.  
![alt text](image-2.png ':size=x250')

You can see the boards' difference between the two projects. Maybe they use different board libraries. But why? I guess WOKWI just wants to make sure that users won't make a conflict when they are using the internal SPI flash memory. Eventhough users don't use it, D2 is still occupied.  
![alt text](image-3.png ':size=600')  
So there are two ways to solve this problem:
1. Use another GPIO instead of D2.
2. Use the starter template.  


![alt text](image-4.png ':size=x250')
