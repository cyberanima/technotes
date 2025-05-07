# Manual for Retrieving Weather Data via OpenWeatherMap API with ESP32S3
## Objective
1. Learn to connect ESP32S3 to Wi-Fi  
2. Make API requests to OpenWeatherMap  
3. Parse JSON data  
4. Display weather information (temperature, humidity, wind speed, etc.).  
## Materials Required
1. Xiao ESP32S3 development board
2. USB cable (for programming and power)
3. Computer with Thonny IDE installed
4. Active Wi-Fi network (SSID and password)
5. OpenWeatherMap API key (obtained from openweathermap.org)
## Experimental Steps
1. <b>Obtain OpenWeatherMap API Key</b>  
Go to OpenWeatherMap API Key Registration. Sign up for a free account and retrieve your API key from the API Keys tab.  
2. Prepare the MicroPython Script  
Create a ```boot.py``` with the code in <u>textbook</u>, replacing placeholders (SSID, password, city, country code, API key):  
3. Upload and Run the Script  
Connect the Xiao ESP32S3 to the computer via USB. Use Thonny IDE to upload the boot.py script to the board and execute the script.
4. Expected Output  
Successful Wi-Fi connection with IP address displayed. And parsed weather data including:  
- Location (city + country)
- Weather description (e.g., "Clouds", "Clear")
- Temperature (in °C, converted from Kelvin)
- Humidity (%)
- Wind speed (m/s)  
## Extension Task -- Display Weather on OLED Screen
Modify the script to include OLED display functionality. Display the weather information on the OLED screen.

# Report for Experiment2 Retrieving Weather Data via OpenWeatherMap API with ESP32S3
**Number:**  
**Name:**  

**Step 1** Code  
**Write the code below.**  

**Step 2** Run the code on hardware.  
**Paste the picture of the running results below.**

**Step 3** Extension Task -- Display Weather on OLED Screen  
**Write the code below.**  
**Paste the picture of the running results below.**  

>Read the textbook  
```pdf
ed/Exp2/api.pdf
```