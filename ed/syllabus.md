# Outline

>1. Digital Fundamentals



## 1. Course Introduction (MODULE 0)
### 1.1 Course Overview
- This course centers on programming ESP32 and ESP8266 edge devices using Micropython. It explores the application of Micropython in real - world scenarios, like IoT and smart device development.
- It helps students understand the significance of Micropython programming in modern technology fields and its potential for innovation.
### 1.2 Course Objectives
- Students will master fundamental Micropython programming skills applicable to ESP32 and ESP8266, including syntax, data types, and control structures.
- They will be able to design and implement complex IoT projects, from simple tasks like LED control to advanced functions such as sensor - based data analytics and device - to - device communication.
- The course aims to cultivate students' problem - solving abilities, enabling them to troubleshoot programming issues and optimize code for better performance.
## 2. Development Environment Setup (PART OF MODULE 1)
### 2.1 Installing uPyCraft IDE
#### 2.1.1 Windows Installation
- Guide students through downloading the uPyCraft IDE installer for Windows. Explain the installation steps, including choosing the installation directory and creating desktop shortcuts.
- Provide solutions for common issues during installation, such as compatibility problems or incorrect file paths.
#### 2.1.2 Mac OS X Installation
- Instruct on downloading the appropriate uPyCraft IDE package for Mac OS X. Detail the installation process, which may involve extracting files and granting necessary permissions.
- Address potential challenges, like issues with the Mac's security settings preventing the installation of unsigned software.
#### 2.1.3 Linux Ubuntu Installation
- Teach students how to install uPyCraft IDE on Ubuntu using the command - line. This includes updating software repositories, installing dependencies, and running the installation script.
- Offer troubleshooting tips for common errors during the Linux installation, such as missing packages or incorrect command syntax.
### 2.2 Flashing Micropython Firmware
- Explain the importance of flashing Micropython firmware onto ESP32 and ESP8266 devices. Discuss how different firmware versions may offer various features and compatibility levels.
- Demonstrate the firmware - flashing process, including connecting the device to the computer, selecting the correct firmware file, and using the appropriate flashing tool. Provide precautions to avoid bricking the device during flashing.
### 2.3 Introduction to Development Boards
#### 2.3.1 ESP32 Board
- Introduce the hardware features of the ESP32 board, such as its microcontroller capabilities, GPIO pins, communication interfaces (Wi - Fi, Bluetooth), and power management.
- Explain how these features can be utilized in Micropython programming for various applications, like building smart home devices or environmental monitors.
#### 2.3.2 ESP8266 Board
- Describe the characteristics of the ESP8266 board, highlighting its strengths in Wi - Fi connectivity and low - cost implementation.
- Compare it with the ESP32 board, emphasizing scenarios where the ESP8266 might be a more suitable choice, such as simple IoT projects with limited resource requirements.
## 3. Python/Micropython Programming Basics (MODULE 2)
### 3.1 Data Types and Variables
- Teach basic Micropython data types, including integers, floating - point numbers, strings, booleans, and lists. Use examples to illustrate how to declare and use variables of different types.
- Explain variable scope, naming conventions, and how variables store and manipulate data within a program.
### 3.2 Operators and Expressions
- Cover arithmetic, comparison, logical, and assignment operators in Micropython. Show how these operators are used to create expressions and perform calculations.
- Provide examples to clarify operator precedence and how it affects the evaluation of complex expressions.
### 3.3 Control Structures
#### 3.3.1 Conditional Statements
- Teach if, if - else, and if - elif - else statements in Micropython. Use real - world examples to demonstrate how conditional statements are used to make decisions in a program.
- Guide students on how to write efficient conditional logic to handle different scenarios based on input or program state.
#### 3.3.2 Loop Statements
- Introduce for and while loops in Micropython. Explain how they are used to iterate over data structures or execute a block of code repeatedly.
- Provide examples of using loops for tasks like summing a list of numbers, iterating through a range of values, or processing data until a certain condition is met.
## 4. GPIO Interaction (MODULE 3)
### 4.1 LED Control
- Explain the principle of LED operation and how it connects to ESP32/ESP8266 GPIO pins. Provide circuit diagrams for reference.
- Write code examples to demonstrate how to turn an LED on, off, and make it blink using Micropython. Guide students through understanding GPIO pin configuration and digital output control.
### 4.2 Digital Inputs and Outputs
- Define digital inputs and outputs in the context of ESP32/ESP8266 programming. Show how to connect external devices (like buttons or switches) as digital inputs and control devices (such as relays) as digital outputs.
- Write code to read digital input states and use them to control digital outputs, creating simple logic circuits in software.
### 4.3 Analog Inputs
- Explain the concept of analog - to - digital conversion (ADC) and how ESP32/ESP8266 boards handle analog inputs.
- Connect an analog sensor (e.g., a potentiometer or a light - dependent resistor) to the board's analog input pin. Write code to read analog sensor values and convert them into meaningful data, such as voltage levels or sensor - specific readings.
### 4.4 PWM - Pulse Width Modulation
- Teach the principle of PWM and its applications, such as controlling the speed of a DC motor or the brightness of an LED.
- Write Micropython code to generate PWM signals on ESP32/ESP8266 GPIO pins. Show how to adjust the duty cycle of the PWM signal to achieve different levels of control.
### 4.5 ESP32 Touch Pins
- Introduce the unique touch - sensing capabilities of ESP32 touch pins. Explain how they work and their advantages over traditional digital input methods.
- Write code to detect touch events on ESP32 touch pins. Demonstrate applications like touch - controlled LED lighting or interactive user interfaces.
### 4.6 Interrupts
- Explain the concept of interrupts in microcontroller programming and how they are implemented in ESP32/ESP8266 using Micropython.
- Write code to set up external interrupts and timer interrupts. Show how interrupts can be used to handle asynchronous events, such as responding to a button press without constantly polling the input pin.
### 4.7 Timers
- Teach the working principle of timers in Micropython for ESP32/ESP8266. Explain how timers can be used for tasks like scheduling code execution at specific intervals or measuring time intervals.
- Write code to configure and use hardware timers, including setting the timer period, enabling timer interrupts, and handling timer - related events.
### 4.8 Deep Sleep with Timer Wake Up
- Explain the deep - sleep mode of ESP32/ESP8266 and its benefits in terms of power conservation.
- Write code to put the device into deep - sleep mode and wake it up using a timer. Demonstrate how this can be used in battery - powered IoT devices to extend battery life.
## 5. Web Servers and HTTP Clients (MODULE 4)
### 5.1 Web Server Basics
- Introduce the concept of web servers and their role in IoT applications. Explain how ESP32/ESP8266 can be used to create a web - server to enable remote device control and monitoring.
- Discuss the technologies and protocols involved in setting up a web server on these microcontrollers, such as the HTTP protocol and socket programming.
### 5.2 Web Server Practice
#### 5.2.1 "Hello world" Web Server
- Write a simple Micropython code to create a "Hello world" web server on ESP32/ESP8266. Guide students through the process of setting up a basic HTTP server and handling client requests.
- Explain how to test the web server using a web browser and understand the basic communication between the client and the server.
#### 5.2.2 Control Outputs
- Expand the web - server functionality to control ESP32/ESP8266 GPIO outputs through a web interface. Teach students how to create HTML forms and use JavaScript to send commands to the server.
- Write code to receive and process these commands on the server - side and control external devices accordingly.
#### 5.2.3 Web Server with a Slider Switch
- Add a slider - switch component to the web interface. Explain how to use HTML5 input elements and JavaScript to create an interactive slider.
- Write code to read the slider position on the server - side and use it to control a PWM - enabled device, such as a variable - speed fan or a dimmable light.
#### 5.2.4 Display Temperature and Humidity Readings
- Connect a temperature and humidity sensor to ESP32/ESP8266. Write code to read sensor data and display it on a web page in real - time.
- Teach students how to use AJAX (Asynchronous JavaScript and XML) or WebSockets to update the web page without refreshing, providing a seamless user experience.
### 5.3 HTTP Clients
#### 5.3.1 Send Sensor Readings via Email (IFTTT)
- Explain the concept of using an HTTP client to send data to an external service, such as IFTTT (If This Then That) to send sensor readings via email.
- Write code to make HTTP POST requests to the IFTTT webhooks, passing sensor data as parameters. Guide students through setting up IFTTT applets to receive and process the data.
#### 5.3.2 Getting Data Using an API
- Teach students how to use Micropython to make HTTP GET requests to third - party APIs to retrieve data. Use examples like getting weather data or stock prices.
- Parse the JSON or XML data returned by the API and display or use the data in the ESP32/ESP8266 project.
## 6. MQTT Protocol (MODULE 5)
### 6.1 MQTT Protocol Basics
- Introduce the MQTT protocol, its lightweight nature, and its significance in IoT communication. Explain the publish - subscribe model, topics, and messages.
- Compare MQTT with other communication protocols and highlight its advantages in scenarios with limited bandwidth and power resources.
### 6.2 Installing Mosquitto MQTT Broker on a Raspberry Pi
- Guide students through the process of installing the Mosquitto MQTT broker on a Raspberry Pi. This includes updating the Raspberry Pi's software repositories, installing Mosquitto and its dependencies, and configuring the broker.
- Explain how to secure the MQTT broker with authentication and encryption to protect data in transit.
### 6.3 MQTT - Establishing a Two - way Communication
- Write Micropython code for ESP32/ESP8266 to establish a connection with the Mosquitto MQTT broker. Demonstrate how to publish messages to topics and subscribe to topics to receive messages.
- Create scenarios where multiple ESP32/ESP8266 devices communicate with each other through the MQTT broker, such as a smart home system where devices exchange status information.
### 6.4 Installing Node - RED and Node - RED Dashboard on a Raspberry Pi
- Instruct students on installing Node - RED and the Node - RED Dashboard on a Raspberry Pi. Explain how Node - RED simplifies the development of IoT applications with its visual programming interface.
- Show how to use Node - RED to create flows for processing MQTT messages, performing data analytics, and controlling ESP32/ESP8266 devices.
### 6.5 MQTT - Connect ESP32/ESP8266 to Node - RED
- Write code to connect ESP32/ESP8266 to Node - RED using the MQTT protocol. Demonstrate how to send and receive data between the devices and Node - RED.
- Use Node - RED Dashboard to create a user - friendly interface for monitoring and controlling ESP32/ESP8266 devices, such as visualizing sensor data or sending commands to actuators.
## 7. Other Components (MODULE 6)
### 7.1 OLED Display
- Introduce the OLED display and its working principle. Explain the connection between the OLED display and ESP32/ESP8266, including the use of communication protocols like I2C or SPI.
- Write Micropython code to initialize the OLED display and display text, numbers, and graphics. Show how to update the display in real - time with sensor data or other relevant information.
### 7.2 DC Motor Control
- Teach the working principle of DC motors and how to control them using ESP32/ESP8266. Explain the use of H - bridges or motor - driver modules for driving the motor.
- Write code to control the speed and direction of a DC motor using PWM signals. Demonstrate applications like building a simple robot or a motor - controlled device.
### 7.3 Addressable RGB LED Strip
- Introduce addressable RGB LED strips, such as WS2812B. Explain how they work and how to connect them to ESP32/ESP8266.
- Write Micropython code to control the color and brightness of individual LEDs in the strip. Create animations like running lights or color fades to showcase the capabilities of the LED strip.
## 8. Thonny IDE (MODULE 7)
### 8.1 Flashing Micropython Firmware (esptool.py)
- Explain the use of esptool.py in Thonny IDE for flashing Micropython firmware. Guide students through the process of selecting the correct device, firmware file, and flashing options.
- Provide troubleshooting steps for common issues during the flashing process, such as communication errors or incorrect firmware versions.
### 8.2 Installing Thonny IDE
- Teach students how to install Thonny IDE on different operating systems (Windows, Mac OS X, Linux). Provide links to the official Thonny website for downloading the installer.
- Explain the installation process, including any additional dependencies or configurations required.
### 8.3 Thonny IDE Overview
- Introduce the interface of Thonny IDE, including the code editor, debugger, and device manager. Explain how to create, open, and save Micropython projects in Thonny.
- Demonstrate basic features like code highlighting, autocompletion, and syntax checking to help students write code more efficiently.
### 8.4 Troubleshooting Tips for Thonny IDE
- Provide solutions for common problems students may encounter while using Thonny IDE, such as connection issues with ESP32/ESP8266 devices, code compilation errors, or problems with the debugger.
- Encourage students to use the Thonny IDE community forums or official documentation for further assistance.
## 9. Course Summary and Project Work
### 9.1 Course Summary
- Review the key concepts covered in the course, including Micropython programming, ESP32/ESP8266 hardware usage, communication protocols, and interaction with external components.
- Emphasize the practical applications of the learned skills in IoT development and encourage students to continue exploring and innovating in this field.
### 9.2 Project Work
- Assign a final project that requires students to apply all the knowledge and skills they have learned throughout the course. The project could be a complete IoT system, such as a smart greenhouse or a home security system.
- Guide students through the project development process, from requirements analysis and design to implementation and testing. Encourage teamwork and creativity in project execution.
- Organize project presentations where students can showcase their work, share their experiences, and learn from each other. 