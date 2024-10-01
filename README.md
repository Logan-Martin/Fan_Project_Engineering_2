# Fan-Project-Engineering-2
## Logan & Jai
---
## Table of Contents
* [List of Materials](#List-of-Materials)
* [Links to Our Documents](#Documents)
* [Psuedo Code](#PsuedoCode)
* [Sketches-Old](#Sketches-Old)
* [Goals](#Goal)
* [What the Final Result Should be](#End-Result)
* [March 1st Notebook( Used for Documenting, Skip if you want )](#March1stNotebook)
* [March19thNotebook( Used for Documenting, Skip if you want )](#March19thNotebook)
* [Work as of May25th ( Used for Documenting, Skip if you want )](#Work-as-of-May25th)
* [June4thNotebook( Used for Documenting, Skip if you want )](#June4thNotebook)



### List of Materials
 - 1x Breadboard 
 - 1x DC Motor
 - 6x Volt battery
 - 1x Ultra sonic sensor
 - 1x Arduino uno board ( we used a Metro board )
 - 1x 270 Ω Resistor
 - 1x Diode
 - 1x potentiometer
 - 1x Transistor
 - 8x Wires ( Male both sides )
 - 4x Wires ( Female to Male )
 - 1x Fanblade ( We used one from a drone, but there are better ones you could use.)
 
  #### Info for the fan blade:
  - I suggest finding some on google or Youtube, many downloadable fanblades exist. 
  - 3d printing them or laser cutting any fan blade will take time, so pre-made ones are easier to use.
 
 #### Other things Needed:
 - Onshape or any cad website or software 
 - A Laser cutting machine ( you can use any material for it, but we used acrylic sheets )
 - A 3d printer, but only if you want to make the motor mound. ( We just taped the motor onto a wall )
 - To run the code at the very bottom of this GitHub, You will need Arduino Create's Web editor.
 - Time ( Took us a year or so, but could take you about an hour or two )
 


### Documents
| Name of Doc. | Link for Doc.  |
| :---         |     ---:       |
| Onshape Document   | [Here](https://cvilleschools.onshape.com/documents/6c10221f72a62c5827a6a0c3/w/3b80432359eea0806169af69/e/17e8b70e5e62a82d1227d98c)     |
| Pre-Planing Document  | [Here](https://docs.google.com/document/d/1r2iU-Si7RD9-BX3SUI-XrdDTprjM076UKu1Y0U7GHaY/edit?usp=sharing)      |

### Goal
``` 
The goal of this project is to make a mobile arduino powered fan to cool down rooms.
```


### Sketches-Old
<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoFanPitchv2.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/Screenshot%20(45).png" width="300" height="300">



### Code
 Short Explaination of what i need code to do:
  When my hand gets close enough, then the sensor powers the fan ( motor ) on.
  Then when my hand gets close again, the fan turns off.
  
  As of right now I don't know if I should have a power control feature. ( this feature has been added, but the box must be taken apart to change the fan speed )
<details>
  
 
<summary>This is Old Code ( DO NOT USE FOR FAN TO WORK )</summary>
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

### Work as of May25th
1st image is the coding as of right,the 2nd image is the layed out box ready to be laser cut:

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoCodeFromAWhileAgoThatMightNotWorkYEahNICEFileNAme.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/LayedOutBox.png" width="300" height="300">

1st image is the inside of the box, the 2nd image is the holder for the motor:

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/InsideBox.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/MotorHolder.png" width="300" height="300">



  
 ### June4thNotebook
  
We have officially started fabricating and should be done by June 9th. ( small notebook, but everything was kind of already done. )
 
 ### End-Result
  
 <details>
<summary>Coding Here ( click the triangle bit ) </summary>
<br>

```
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
```
</details>
 
 
 Final wiring Here:
 
 
 <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/WiringForFanBox.png" width="500" height="500">
  
[Back to Table of Contents](#Table-of-Contents)
