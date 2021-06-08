# Fan-Project-Engineering-2
## Logan & Jai
---
## Table of Contents
* [Links to Documents](#Documents)
* [Sketches-Old](#Sketches-Old)
* [Psuedo Code](#PsuedoCode)
* [Goals](#Goal)
* [March 1st Notebook](#March1stNotebook)
* [March19thNotebook](#March19thNotebook)
* [May25thNotebook](#May25thNotebook)
* [June4thNotebook](#June4thNotebook)
* [End Result](#End-Result)
### Goal
``` 
The goal of this project is to make a mobile arduino powered fan to cool down rooms.
```


### Documents
| Name of Doc. | Link for Doc.  |
| :---         |     ---:       |
| Onshape Document   | [Here](https://cvilleschools.onshape.com/documents/6c10221f72a62c5827a6a0c3/w/3c881ee184980c73d02d8186/e/a389b126452617b6238eb00f)     |
| Pre-Planing Document  | [Here](https://docs.google.com/document/d/1r2iU-Si7RD9-BX3SUI-XrdDTprjM076UKu1Y0U7GHaY/edit?usp=sharing)      |


### Sketches-Old
<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoFanPitchv2.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/Screenshot%20(45).png" width="300" height="300">



### Code
 Short Explaination of what i need code to do:
  When my hand gets close enough, then the sensor powers the fan ( motor ) on.
  Then when my hand gets close again, the fan turns off.
  
  As of right now I don't know if I should have a power control feature.
<details>
  
 
<summary>This is the Code</summary>
<br>
  
```c
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
  
 
</details>


### March1stNotebook
| Name      | Answer   |
| :---      | ---:     |
| Logan     | On track, My side of Cad is basically done and Coding is almost done. Although I do need to wire things and code for the ultra sonic sensor. |
| Jai       | On track, I do more of the assembly in onshape like working on the box and putting the different pieces in, we are still figuring out where we want to put different stuff but we are almost done. |

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoMotorWiring.PNG" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/WIN_20210302_10_36_49_Pro.jpg" width="300" height="300">

### March19thNotebook
| Question      | Answer   |
| :---      | ---:     |
| "What major obstacle is keeping you from making better progress on your project?" | Coding things is a massive issue that is holding us back.|

## Photos / Screen Shots
<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/Screenshot%20(79).png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/Screenshot%20(80).png" width="300" height="300">

### May25thNotebook
1st image is the coding as of right,the 2nd image is the layed out box ready to be laser cut:

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoCodeFromAWhileAgoThatMightNotWorkYEahNICEFileNAme.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/LayedOutBox.png" width="300" height="300">

1st image is the inside of the box, the 2nd image is the holder for the motor:

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/InsideBox.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/MotorHolder.png" width="300" height="300">


<details>
<summary>Coding as of 5/27/2021</summary>
<br>
#include <NewPing.h>

#define TRIGGER_PIN  12  // Arduino pin tied to trigger pin on the ultrasonic sensor.
#define ECHO_PIN     11  // Arduino pin tied to echo pin on the ultrasonic sensor.
#define MAX_DISTANCE 200 // Maximum distance we want to ping for (in centimeters). Maximum sensor distance is rated at 400-500cm.



NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE); // NewPing setup of pins and maximum distance.


int distance = 0;
int motorVal = 0;

int potPin = 0;         // the number of the input pin Pot Pin
int motorPin = 9;       // the number of the output pin

int state = HIGH;      // the current state of the output pin
int reading;           // the current reading from the input pin
int previous = LOW;    // the previous reading from the input pin
int FanSpeed = 0;      // variable for motor speed

// the follow variables are long's because the time, measured in miliseconds,
// will quickly become a bigger number than can be stored in an int.
long time = 0;         // the last time the output pin was toggled
long debounce = 1000;   // the debounce time, increase if the output flickers

void setup()
{
  Serial.begin(9600);


  pinMode(potPin, INPUT);
  pinMode(motorPin, OUTPUT);
}

void loop()
{
  delay(50);
  distance = sonar.ping_cm();

  if (distance != 0 && distance < 99) {

    if (distance <= 30 && previous > 30 && millis() - time > debounce) { //if the value is correct, and the previous value was incorrent
      //AND if its been at least 1 second since the last time I changed the state.
      if (state == HIGH) {
        state = LOW;
      }
      else {
        state = HIGH;
      }

      time = millis();
    }
  }

  if (state == HIGH ) {
    FanSpeed = map(analogRead(potPin), 0, 1023, 0, 255);
    analogWrite(motorPin, FanSpeed);
  }
  else {
    FanSpeed = 0;
    analogWrite(motorPin, FanSpeed);
  }

  digitalWrite(13, state);
  Serial.print(state);
  Serial.print("\t Ping: ");
  Serial.print(distance); // Send ping, get distance in cm and print result (0 = outside set distance range)
  Serial.print("\t");
  Serial.println(FanSpeed);

  previous = distance;
}
</details>
  
 ### June4thNotebook
  
We have officially started fabricating and should be done by June 9th.
 
 ### End-Result
 
 <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/FanboxInRealLifeEngineeringCrap.jpg" width="300" height="300">
  
[Back to Table of Contents](#Table-of-Contents)
