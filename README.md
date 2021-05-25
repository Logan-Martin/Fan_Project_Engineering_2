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
  
  
  Short Explaination of what i need code to do:
  When my hand gets close enough, then the sensor powers the fan ( motor ) on.
  Then when my hand gets close again, the fan turns off.
  
  As of right now I don't know if I should have a power control feature.
```
Code above from Arduino's code examples for the ultra sonic sensor.

### March1stNotebook
| Name      | Answer   |
| :---      | ---:     |
| Logan     | On track, My side of Cad is basicly done and Coding is almost done. Although I do need to wire things and code for the ultra sonic sensor. |
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

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoCodeFromAWhileAgoThatMightNotWorkYEahNICEFileNAme.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoCodeFromAWhileAgoThatMightNotWorkYEahNICEFileNAme.png" width="300" height="300">

1st image is the full box, the 2nd image is the holder for the motor:

<img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoCodeFromAWhileAgoThatMightNotWorkYEahNICEFileNAme.png" width="300" height="300"> <img src="https://github.com/Logan-Martin/Fan-Project-Engineering-2/blob/main/ArduinoCodeFromAWhileAgoThatMightNotWorkYEahNICEFileNAme.png" width="300" height="300">

[Back to Table of Contents](#Table-of-Contents)
