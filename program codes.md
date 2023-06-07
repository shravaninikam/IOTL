##### Program 5
Write a program using Arduino to control LED (one or more) blinking.
```cpp
int ledPin = 13; // Pin connected to the LED

void setup()
{
  pinMode(ledPin, OUTPUT); // Set the LED pin as an output
}
void loop()
{
  digitalWrite(ledPin, HIGH); // Turn on the LED by setting the pin to HIGH
  delay(1000);                // Delay for 1 second (1000 milliseconds)

  digitalWrite(ledPin, LOW); // Turn off the LED by setting the pin to LOW
  delay(1000);               // Delay for 1 second (1000 milliseconds)
}
```

##### Program 6
Create a program that illuminates the green LED if the counter is less than 100, illuminates the yellow LED if the counter is between 101 and 200 and illuminates the red LED if the counter is greater than 200
```python
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BOARD)
GPIO.setwarnings(False)

GPIO.setup(36, GPIO.OUT)  # Pin 36 as output for the first LED
GPIO.setup(38, GPIO.OUT)  # Pin 38 as output for the second LED
GPIO.setup(40, GPIO.OUT)  # Pin 40 as output for the third LED

counter = 10  # Starting counter value

while True:
    if counter < 100:
        GPIO.output(36, GPIO.HIGH)  # Turn on the first LED
        GPIO.output(38, GPIO.LOW)   # Turn off the second LED
        GPIO.output(40, GPIO.LOW)   # Turn off the third LED
        time.sleep(2)
        counter += 100
    elif 100 <= counter < 200:
        GPIO.output(36, GPIO.LOW)    # Turn off the first LED
        GPIO.output(38, GPIO.HIGH)   # Turn on the second LED
        GPIO.output(40, GPIO.LOW)    # Turn off the third LED
        time.sleep(2)
        counter += 100
    else:
        GPIO.output(36, GPIO.LOW)    # Turn off the first LED
        GPIO.output(38, GPIO.LOW)    # Turn off the second LED
        GPIO.output(40, GPIO.HIGH)   # Turn on the third LED
        time.sleep(2)
        counter = 1  # Reset the counter value to 1


```

##### Program 7
Create a program so that when the users enter G the green light blinks, when Y the yellow light illuminates and R the red light illuminates.
```python
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BOARD)
GPIO.setwarnings(False)

GPIO.setup(36, GPIO.OUT)  # Pin 36 as output for the first LED
GPIO.setup(38, GPIO.OUT)  # Pin 38 as output for the second LED
GPIO.setup(40, GPIO.OUT)  # Pin 40 as output for the third LED


while True:
    input1 = input("Enter color (Y for yellow, G for green, any other key for red): ")
    if input1 == 'Y':
        GPIO.output(36, GPIO.HIGH)  # Turn on the first LED (yellow)
        GPIO.output(38, GPIO.LOW)   # Turn off the second LED (green)
        GPIO.output(40, GPIO.LOW)   # Turn off the third LED (red)
        time.sleep(2)
    elif input1 == 'G':
        GPIO.output(36, GPIO.LOW)    # Turn off the first LED (yellow)
        GPIO.output(38, GPIO.HIGH)   # Turn on the second LED (green)
        GPIO.output(40, GPIO.LOW)    # Turn off the third LED (red)
        time.sleep(2)
    else:
        GPIO.output(36, GPIO.LOW)    # Turn off the first LED (yellow)
        GPIO.output(38, GPIO.LOW)    # Turn off the second LED (green)
        GPIO.output(40, GPIO.HIGH)   # Turn on the third LED (red)
        time.sleep(2)

```

##### Program 8
Write a program to control color of LED by turning three different potentiometer. One will read for the value of red, one for the value of green, and one for the value of blue.
```cpp
const int redPin = 9;    // Pin for red LED
const int greenPin = 10; // Pin for green LED
const int bluePin = 11;  // Pin for blue LED

const int redPotPin = A0;    // Pin for red potentiometer
const int greenPotPin = A1;  // Pin for green potentiometer
const int bluePotPin = A2;   // Pin for blue potentiometer

void setup() {
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);
  
  // Start serial communication
  Serial.begin(9600);
}

void loop() {
  // Read values from the potentiometers
  int redValue = analogRead(redPotPin);
  int greenValue = analogRead(greenPotPin);
  int blueValue = analogRead(bluePotPin);
  
  // Map the analog values (0-1023) to PWM range (0-255)
  int redPWM = map(redValue, 0, 1023, 0, 255);
  int greenPWM = map(greenValue, 0, 1023, 0, 255);
  int bluePWM = map(blueValue, 0, 1023, 0, 255);
  
  // Set the LED colors
  analogWrite(redPin, redPWM);
  analogWrite(greenPin, greenPWM);
  analogWrite(bluePin, bluePWM);
  
  // Print the RGB values to the serial monitor
  Serial.print("Red: ");
  Serial.print(redPWM);
  Serial.print(" Green: ");
  Serial.print(greenPWM);
  Serial.print(" Blue: ");
  Serial.println(bluePWM);
  
  delay(100); // Delay for smooth color transitions
}
```

##### Program 9
Write a program to read the temperature sensor and send the values to the serial monitor on computer.
```python
import Adafruit_DHT as Ada

while True:
    h, t = Ada.read_retry(11, 4)
    # Read temperature and humidity from DHT sensor connected to GPIO pin 4
    # The first argument is the sensor type (11 for DHT11, 22 for DHT22)
    # The second argument is the GPIO pin number

    print("\nTemperature Reading:", t)
    print("Humidity Reading:", h)
    # Print the temperature and humidity readings

    break
    # Break the loop after reading the values once
```

##### Program 10
Write a program so it displays the temperature in Fahrenheit as well as the maximum and minimum temperature it has seen
```python
import Adafruit_DHT as Ada

while True:
    h, t = Ada.read_retry(11, 4)
    # Read temperature and humidity from DHT sensor connected to GPIO pin 4
    # The first argument is the sensor type (11 for DHT11, 22 for DHT22)
    # The second argument is the GPIO pin number

    print("\nTemperature Reading:", t)
    f = (t * 1.8) + 32
    print("Temperature Reading in F:", f)
    print("Humidity Reading:", h)
    # Print the temperature reading in Celsius and Fahrenheit, and the humidity reading

    min_temp = 50
    max_temp = 80
    # Set initial minimum and maximum temperature values

    for _ in range(5):
        if t < min_temp:
            min_temp = t
        time.sleep(2)
    print("\nMin Temp:", min_temp)
    # Update minimum temperature if a lower value is found within 5 iterations

    for _ in range(5):
        if t > max_temp:
            max_temp = t
        time.sleep(2)
    print("Max Temp:", max_temp)
    # Update maximum temperature if a higher value is found within 5 iterations
```

##### Program 11
Write a program using piezo element and use it to play a tune after someone knocks
```cpp
const int piezoPin = A1;    // Pin for the piezo buzzer
const int touchSensor = A0; // Pin for the touch sensor

void setup() {
  Serial.begin(9600);    // Initialize serial communication at 9600 baud rate
  pinMode(A1, OUTPUT);   // Set piezo pin as OUTPUT
  pinMode(A0, INPUT);    // Set touch sensor pin as INPUT
}

void loop() {
  int melody[] = {262, 294, 330, 349, 392, 440, 494, 523};  // Array of melody frequencies
  int value = analogRead(A0);  // Read analog value from touch sensor
  Serial.print(value);   // Print the analog value to the serial monitor
  Serial.println();      // Move to the next line
  
  if (value < 200) {
    // If touch sensor value is less than 200, play the melody
    for (int i = 0; i < 8; i++) {
      tone(A1, melody[i]);   // Generate tone on the piezo pin
      delay(1000);           // Play each note for 1 second
    }
  } else {
    noTone(A1);   // If touch sensor value is greater than or equal to 200, stop generating tone
  }
  
  delay(1000);   // Delay for 1 second before repeating the loop
}

```

##### Program 12
Understanding the connectivity of Raspberry PI with IR sensor. Write an application to detect obstacle and notify the user using LEDs
```python
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BOARD)
GPIO.setup(40, GPIO.IN)
GPIO.setup(3, GPIO.OUT)

while True:
    # Read the input value from the obstacle sensor
    i = GPIO.input(40)

    if i == 0:
        print("Obstacle Detected!")
        GPIO.output(3, GPIO.HIGH)
        # Turn on the LED connected to pin 3
        time.sleep(2)
        # Wait for 2 seconds
    else:
        print("Obstacle not Detected!")
        GPIO.output(3, GPIO.LOW)
        # Turn off the LED connected to pin 3
        time.sleep(2)
        # Wait for 2 seconds
```

