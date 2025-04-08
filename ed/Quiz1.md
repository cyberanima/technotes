# ```Quiz1``` -- <u>13:30 - 16:30</u>, submit in <u>pdf</u> format.

1. Write out the truth table for the following logic gates.  
![alt text](Quiz1/image.png ':size=100')  
![alt text](Quiz1/image-1.png ':size=100')  
![alt text](Quiz1/image-2.png ':size=100')  

2. Verify the function of the following logic circuit using [Logic Gate Simulator](https://academo.org/demos/logic-gate-simulator/). Write out the truth table.  
![alt text](Quiz1/image-3.png ':size=600')  
Truth Table:  
| A | B | C | D | X |  
| 0 | 0 | 0 | 0 | ? |  
| 0 | 0 | 0 | 1 | ? |  
| 0 | 0 | 1 | 0 | ? |  
......

3. Design a DVM in [TinkerCAD](https://www.tinkercad.com/). Use the following materials: Arduino, Function Generator, Oscilloscope, Breadboard and a few wires. Display the Triangle wave (Frequency=10Hz, Amplitude=2V, DC Offset=1V) on the oscilloscope and Serial Monitor simulaneously.

4. Use one GPIO to control two LEDs to flash alternately in [wokwi](https://wokwi.com/). Use the following materials: ESP32, NOT Gate, LEDs and resistors.

5. Comment the following code line by line. Describe the function of the whole program.
```python
from machine import Pin
from time import sleep
led = Pin(2, Pin.OUT)
while True:
    led.value(not led.value())
    sleep(0.5)
```

6. Which GPIOs are connected to I2C OLED, User LED, User Button and Buzzer seperately? 
![alt text](Quiz1/image-4.png ':size=600')

7. Which package needs to be installed to use the I2C OLED in Thonny?

8. Write a program to control the I2C OLED to display the following message: "Hello World!". Comment on each line of the code.

9. Comment the following code line by line. Describe the function of the whole program.  
![alt text](Quiz1/image-5.png ':size=600')
```python
from machine import Pin
from time import sleep
led = Pin(5, Pin.OUT)
button = Pin(4, Pin.IN)
while True:
  led.value(button.value())
  sleep(0.1)
```

10. Programming to implement LED blink, based on touchpad value.

11. Comment the following code line by line. Describe the difference between touchpad GPIO and button GPIO.  
```python
import time
from machine import Pin
led = Pin(21, Pin.OUT)
btn = Pin(2, Pin.IN, Pin.PULL_UP)
while True:
    led.value(btn.value())
    time.sleep(0.1)
```

12. Which GPIO is the buzzer pin? Programming to implement the buzzer beep in 440Hz.

13. Comment the following code line by line. Describe the function of the whole program.  
![alt text](Quiz1/image-6.png ':size=600')
```python
from machine import Pin, ADC
from time import sleep
pot = ADC(Pin(34))
pot.atten(ADC.ATTN_11DB)
pot.width(ADC.WIDTH_12BIT)
while True:
  pot_value = pot.read()
  print(pot_value)
  sleep(0.1)
```

14. In Question 13, Line 4 means we want to read voltage from 0 to 3.3V. The ```atten()``` method can take the following arguments. Fill in the voltage range for each argument.  
• ```ADC.ATTN_0DB``` - the full range voltage:   
• ```ADC.ATTN_2_5DB``` - the full range voltage:  
• ```ADC.ATTN_6DB``` - the full range voltage:  
• ```ADC.ATTN_11DB``` - the full range voltage:  

15. In Question 13, Line 5 means when you rotate the potentiometer you get values from 0 to 4095. The ```width()``` method can take the following arguments. Fill in the value range for each argument.  
• ```ADC.WIDTH_9BIT``` - range:    
• ```ADC.WIDTH_10BIT``` - range:  
• ```ADC.WIDTH_11BIT``` - range:  
• ```ADC.WIDTH_12BIT``` - range:  

16. What is PWM? Explain how PWM works according to the following figure.  
![alt text](Quiz1/image-7.png ':size=600')

17. Comment the following code line by line. Describe the function of the whole program.  
```python
from machine import Pin, ADC, SoftI2C
import ssd1306
import math
from time import sleep

pot =ADC(Pin(2))
pot.atten(ADC.ATTN_11DB)
pot.width(ADC.WIDTH_12BIT)

while True:
    pot_value = pot.read()
    print(pot_value)
    pot_value_string = str(pot_value)
    
    i2c = SoftI2C(scl=Pin(6), sda=Pin(5))  
    oled_width = 128
    oled_height = 64
    oled = ssd1306.SSD1306_I2C(oled_width, oled_height, i2c)

    oled.fill(0) 
    oled.text("AnalogRead", 10, 15)
    oled.text(pot_value_string, 30, 40)
    oled.show() 
    
    sleep(0.1)
```

18. What is ```ADC``` and what is ```DAC```? Explain with figures.

19. How to connect ESP32 to the potentiometer pin-to-pin?

20. What is the difference between input and output GPIOs when coding?

21. What are the wireless communication methods of esp32?