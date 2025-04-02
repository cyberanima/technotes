# Manual for Experiment1 LED Dimmer Switch Project

## Objective
Implement real-time LED brightness adjustment using a potentiometer. The system will:
1. Read voltage from a potentiometer via ESP32S3’s ADC.
2. Adjust LED brightness using PWM based on the ADC value.
3. Display the real-time voltage and ```brightness percent **(N%)**``` on an OLED screen.
## Components Required
| Component          | Quantity | Details                          |  
|---------------------|----------|----------------------------------|  
| ESP32-S3 Development Board | 1      | With built-in ADC and PWM support |  
| OLED Display (SSD1306) | 1      | 128x64 pixels, I2C interface      |  
| Potentiometer (10kΩ) | 1      | For voltage adjustment           |  
| LED + 220Ω Resistor | 1      | For current limiting             |  
| Breadboard & Jumper Wires | -      | For circuit connections          |
## Circuit Diagram  
**ESP32-S3 Connections:**  
1. **Potentiometer:**  
   - GND → ESP32S3 GND  
   - VCC → ESP32S3 ```3.3V```  
   - OUT → ADC Pin (e.g., GPIO 34)  
2. **LED:**  
   - Anode → PWM Pin (e.g., GPIO 15)  
   - Cathode → GND via 220Ω resistor  
3. **OLED Display:**  
   - SCL → GPIO 1  
   - SDA → GPIO 2  
   - VCC → 3.3V  
   - GND → GND 

# Report for Experiment1 LED Dimmer Switch Project
**Number:**  
**Name:**  

**Step 1** Simulation of the LED Dimmer Switch Project in Wokwi. In simulation, it's not necessary to connect OLED, but you can display the potentiometer voltage and brightness persent **(N%)** by ```print```.  
**Paste the screenshot of the simulation results below.**

**Step 2** Code for the LED Dimmer Switch Project on hardware.  
**Write the code below.**  

**Step 3** Run the code on hardware.  
**Paste the picture of the running results below.**
