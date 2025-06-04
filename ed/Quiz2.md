# ```Quiz2``` -- <u>13:30 - 16:30</u>, submit in <u>pdf</u> format.

1. Write out the full name of UART.  

2. How many UARTs are there in ESP32S3? Which one is used by MicroPython's REPL? What are the GPIOs corresponding to UART1?  

3. Comment the following code line by line. Describe the function of the whole program.  
```python
# Master
from machine import Pin, UART
import time
uart = UART(1, baudrate=9600, tx=43, rx=44)
while True:
    uart.write('t') 
    time.sleep(5)
```

4. Comment the following code line by line. Describe the function of the whole program.  
```python
# Slave
from machine import Pin, UART
import time
uart = UART(1, baudrate=9600, tx=43, rx=44)
led = Pin(21, Pin.OUT)
while True:
    if uart.any(): 
        data = uart.read() 
        if data == b't':
            led.value(not led.value())
            print(data)
            print(data.decode('utf-8'))
            print(hex(ord(data)))
            print(bin(ord(data)))
    time.sleep(1)
```

5. In the UART "Chat Room" example, there is a multi-line display problem as shown in the figure below. Please explain the reason for the problem and provide solution.  
![alt text](image.png ':size=400')  

6. Open two "sokit" programs on your laptop. One is set as a server and the other is set as a client. Establish a connection between the two programs. Send a message from the client to the server. Then send a message from the server to the client. Use screenshots to prove your results.  

7. In the ESP32S3 Web Server example, what do 'ssid' and 'password' stand for?  

8. In the ESP32S3 Web Server example's ```main.py```, What is displayed on the web homepage? How should the code be modified if you need to display your student ID and name?  
```python
# main.py
def web_page():
  html = """<html><head><meta name="viewport" content="width=device-width, initial-scale=1"></head>
  <body><h1>Hello, World!</h1></body></html>"""
  return html
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind(('', 80))
s.listen(5)
while True:
  conn, addr = s.accept()
  print('Got a connection from %s' % str(addr))
  request = conn.recv(1024)
  print('Content = %s' % str(request))
  response = web_page()
  conn.send('HTTP/1.1 200 OK\n')
  conn.send('Content-Type: text/html\n')
  conn.send('Connection: close\n\n')
  conn.sendall(response)
  conn.close()
```

9. Describe the four pins of the DHT11.  

10. Describe the data format of DHT11.  

11. Check the 40-bit data received is correct or not -- 00110101 00000000 00011000 00000000 01001001.  

12. If the data is correct, what is the temperature and humidity? -- 00110101 00000000 00011000 00000000 01001101  

13. According to the connections between the ESP32S3 and the DHT11, write out the code to read the temperature and humidity from the DHT11.

14. Write out the full name of MQTT. 

15. Determine True or False about MQTT:  
    - Clients do not have addresses like in email systems, and messages are not sent to clients.
    - Messages are published to a broker on a topic.
    - The job of an MQTT broker is to filter messages based on topic, and then distribute them to subscribers.
    - A client can receive these messages by subscribing to that topic on the same broker
    - There is no direct connection between a publisher and subscriber.
    - All clients can publish (broadcast) and subscribe (receive).
    - MQTT brokers do not normally store messages.  

16. Use public MQTT broker to subscribe and publish messages on mobile phone and laptop. Use screenshots to prove your results.

17. Use Mosquitto MQTT broker to subscribe and publish messages on mobile phone and laptop. Use screenshots to prove your results.  

18. Connect DHT11 to your ESP32S3 and program it to read the temperature and humidity values and publish them to the topics -- env; meanwhile, subscribe to the same topic and print the temperature and humidity values to the shell. Use your mobile to subscribe to the topic -- env. Write the code to implement this function and then use screenshots to prove your results.

19. Can the ESP32S3 connect to the campus network? If not, please explain the reason.
