# Fan-Project-Engineering-2
## Logan & Jai
---
## Table of Contents
* [Links to Documents](#Documents)
* [Sketches](#Sketches)
* [Psuedo Code](#PsuedoCode)
* [Goals](#Goal)

### Goal
``` 
My room gets really warm, So the goal of this project is to cool it down. We, Logan and Jai, will reach this goal by creating a mobile arduino powered fan.
```


### Documents
| Name of Doc. | Link for Doc.  |
| :---         |     ---:       |
| Onshape Document   | [Here](https://cvilleschools.onshape.com/documents/6c10221f72a62c5827a6a0c3/w/3c881ee184980c73d02d8186/e/a389b126452617b6238eb00f)     |
| Pre-Planing Document  | [Here](https://docs.google.com/document/d/1r2iU-Si7RD9-BX3SUI-XrdDTprjM076UKu1Y0U7GHaY/edit?usp=sharing)      |


### Sketches
<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoFanPitchv2.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/Screenshot%20(45).png" width="300" height="300">

### PsuedoCode
```
#define echoPin 2 // attach pin D2 Arduino to pin Echo of HC-SR04
#define trigPin 3 //attach pin D3 Arduino to pin Trig of HC-SR04

// defines variables
long duration; // variable for the duration of sound wave travel
int distance; // variable for the distance measurement

void setup() {
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an OUTPUT
  pinMode(echoPin, INPUT); // Sets the echoPin as an INPUT
  Serial.begin(9600); // // Serial Communication is starting with 9600 of baudrate speed
  Serial.println("Ultrasonic Sensor HC-SR04 Test"); // print some text in Serial Monitor
  Serial.println("with Arduino UNO R3");
}
void loop() {
  // Clears the trigPin condition
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  // Sets the trigPin HIGH (ACTIVE) for 10 microseconds
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  // Reads the echoPin, returns the sound wave travel time in microseconds
  duration = pulseIn(echoPin, HIGH);
  // Calculating the distance
  distance = duration * 0.034 / 2; // Speed of sound wave divided by 2 (go and back)
  // Displays the distance on the Serial Monitor
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
```
Code above from Arduino's code examples for the ultra sonic sensor.

[Back to Table of Contents](#Table-of-Contents)
