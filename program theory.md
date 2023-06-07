
### What is IoT?
IoT stands for an Internet of Things. It is largely a network using which matters can talk to  
each other the use of the internet as an approach to communication between them. All of  
the matters should be IP protocol enabled on the way to have this concept viable.

---

### Examples of IoT in our lives?
1. Home Security and Smart Domestic
2. Healthcare
3. Wearable Technology
4. Tracking Assets
5. Connected Car

---

### Raspberry Pi
The Raspberry Pi is a low cost, tiny computer, about the size of a credit card. You can plug  
your keyboard, mouse and your TV into it, and use it just as you would use a PC.

---

### What are GPIO Pins used in Raspberry Pi boards?
GPIO is the acronym for **General Purpose Input Output Pin**. They are more like  
switches on the board that gives an output voltage when high and give no voltage when  
turned to low. This is used in the Raspberry Pi boards to make an interface between the  
Raspberry Pi and all the components of the board. This enables multiple interactions and  
makes internal properties of devices easily available on board.

---

### Raspberry Pi Pins
1. Power Pins:
    - 3.3V: This pin provides a regulated 3.3V power supply.
    - 5V: This pin provides a regulated 5V power supply.
    - GND: These pins are ground connections (0V) used for completing electrical circuits.
2. GPIO Pins:
    - General-purpose Input/Output (GPIO) pins can be configured for digital input or output operations.
    - GPIO2 / SDA: Serial Data Line for I2C communication.
    - GPIO3 / SCL: Serial Clock Line for I2C communication.
    - GPIO4: This pin can be used for various purposes depending on the configuration.
    - GPIO14 / TXD0: Transmit pin for serial communication (UART).
    - GPIO15 / RXD0: Receive pin for serial communication (UART).
    - GPIO17: This pin can be used for various purposes depending on the configuration.
    - GPIO18 / PCM_CLK: Pulse Code Modulation (PCM) Clock pin.
    - GPIO27: This pin can be used for various purposes depending on the configuration.
    - GPIO22: This pin can be used for various purposes depending on the configuration.
    - GPIO23: This pin can be used for various purposes depending on the configuration.
    - GPIO24: This pin can be used for various purposes depending on the configuration.
    - GPIO10 / MOSI: Master Out Slave In pin for SPI communication.
    - GPIO9 / MISO: Master In Slave Out pin for SPI communication.
    - GPIO11 / SCLK: Serial Clock pin for SPI communication.
    - GPIO25: This pin can be used for various purposes depending on the configuration.
    - GPIO8 / CE0: Chip Enable 0 pin for SPI communication.
    - GPIO7 / CE1: Chip Enable 1 pin for SPI communication.
3. Other Pins:
    - ID_SD: I2C EEPROM ID EEPROM data line (reserved for HAT EEPROM).
    - ID_SC: I2C EEPROM ID EEPROM clock line (reserved for HAT EEPROM).
    - 3.3V and 5V: These pins provide power supply voltages of 3.3V and 5V, respectively.
    - GND: These pins are ground connections (0V) used for completing electrical circuits.

It's important to refer to the specific pinout diagram and documentation for the particular Raspberry Pi model you are using, as the number and configuration of the pins may vary between different Raspberry Pi boards.

---

### Arduino
Arduino is an open-source electronics platform that provides a flexible and user-friendly environment for creating interactive projects. It consists of a hardware board with various input and output pins and a software development environment that allows users to write and upload code to the board. Here's some information about Arduino:

1. Arduino Board:
    - Arduino boards come in various models and sizes, but they generally include a microcontroller, input/output pins, power connectors, and USB interfaces.
    - The microcontroller is the brain of the Arduino board, responsible for executing the uploaded code and controlling the connected components.
    - Arduino boards are designed to be easy to use, with a simple interface and a wide range of compatibility with sensors, actuators, and other electronic components.
2. Arduino IDE (Integrated Development Environment):
    - The Arduino IDE is a software development environment used to write, compile, and upload code to the Arduino board.
    - It provides a user-friendly interface and a simplified programming language based on C/C++.
    - The IDE includes a text editor for writing code, a compiler for converting code into machine language, and a bootloader that allows code to be uploaded to the board via USB.
3. Programming Language:
    - Arduino uses a variant of C/C++ programming language.
    - The language is simplified and abstracted to make it more accessible for beginners and non-programmers.
    - The Arduino programming language provides pre-defined functions and libraries that simplify common tasks, such as controlling digital and analog pins, communicating with sensors and other devices, and performing mathematical operations.
4. Libraries and Community:
    - Arduino has a vast collection of libraries that provide pre-written code and functions to extend the capabilities of the board.
    - Libraries cover various functionalities, including communication protocols (e.g., I2C, SPI), displays, sensors, motor control, and more.
    - The Arduino community is active and supportive, with a wealth of online resources, forums, and tutorials available. It makes it easy to find help, share projects, and learn from others.
5. Project Applications:
    - Arduino is widely used in a range of projects and applications, from hobbyist creations to professional prototypes.
    - It is suitable for various fields, including robotics, home automation, Internet of Things (IoT), wearables, art installations, and education.
    - Arduino's versatility, ease of use, and low-cost nature make it accessible to beginners while providing enough flexibility for advanced users.

### What is Adafruit and DHT11 Sensor?
-  The Adafruit_DHT library is a Python library that provides functions for reading data from DHT series temperature and humidity sensors.
    - It simplifies the process of interfacing with DHT sensors by providing convenient methods for reading sensor data.
    - The library supports different DHT sensor models, such as DHT11, DHT22, and AM2302.
- DHT11 Sensor:
    - The DHT11 is a low-cost digital temperature and humidity sensor.
    - It can measure temperatures ranging from 0 to 50 degrees Celsius with an accuracy of ±2 degrees Celsius.
    - The humidity measurement range is 20% to 90% with an accuracy of ±5%.
    - The sensor communicates using a proprietary 1-wire protocol that requires a microcontroller or a computer with GPIO capabilities for data retrieval.

---

### Ardunio Pins
1. Digital Pins:
    - Digital Pin 0 (D0) / RX: Receive pin for serial communication (UART).
    - Digital Pin 1 (D1) / TX: Transmit pin for serial communication (UART).
    - Digital Pins 2 to 13: General-purpose digital input/output (I/O) pins. These can be used for reading digital sensors or controlling digital actuators.
    - Digital Pin 13 (D13): This pin is connected to an onboard LED (usually labeled "L") and is commonly used for simple status indications.
2. Analog Pins:
    - Analog Pins A0 to A5: These pins can be used to read analog voltage levels. They have a 10-bit resolution, allowing for values between 0 and 1023 to be read.
3. Special Pins:
    - 5V and GND: These pins provide the power supply voltage (5V) and ground (0V) respectively.
    - 3.3V: This pin provides a regulated 3.3V power supply.
    - VIN: This pin is used to supply power to the Arduino board, typically from an external power source (7-12V).
    - RESET: This pin is used to reset the microcontroller on the Arduino board.
4. Other Pins:
    - SDA and SCL: These pins are used for I2C communication.
    - PWM Pins (marked with a "~" symbol): Digital pins 3, 5, 6, 9, 10, and 11 can generate Pulse Width Modulation (PWM) signals, allowing for analog-like control of devices such as motors or LEDs.

It's important to note that the specific pin configuration may vary depending on the Arduino board model. The pins mentioned above correspond to the Arduino Uno board, which is one of the most commonly used models. Other Arduino boards may have additional or different pins based on their design and capabilities.

---

### What is IR Sensor?
An infrared (IR) sensor, also known as an infrared detector or IR receiver, is a device that detects and responds to infrared radiation. It is commonly used in various applications, including proximity sensing, object detection, and remote control systems. The IR sensor operates by receiving and interpreting the infrared signals emitted by objects in its detection range.

---

### What is a piezo buzzer and how does it work? 
A piezo buzzer is a small electronic component that can generate sound or tones when an electrical signal is applied to it. It consists of a piezoelectric element, which is a crystal that vibrates when an electric field is applied to it. The vibration of the crystal creates sound waves, producing audible tones. In the provided code, the piezo buzzer connected to pin A1 is used to play a melody by generating different frequencies of tones.
