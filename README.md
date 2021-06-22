# Control-5-servo-motors-using-Arduino-UNO-R3-

## Table of contents
* [Introduction](#Introduction)
* [Technologies](#technologies)
* [Components required](#Components-required)
* [Connections](#Connections)
* [Block diagram & simulation ](#Block-diagram-&-simulation)



## Introduction
This project is to control 5 servo motors using Arduino UNO R3 simulated with TINKERCAD circuit , The servo motor is used in robotics to activate movements, giving the arm to its precise angle , so we used it with several projects like robot arm , spider robot and  robotic vehicle ,We will cover several topics : 👍 
 1. servo motor rotate 90 degrees .
 2. servo motor rotate 90 degrees and back to 0 degree after 3 sec .
 3. Control multiple servo motors using Potentiometers .

## Technologies
Project is created with:
* Arduino IDE 1.18.15 [To Downloud](https://www.arduino.cc/en/software)
* AUTODESK TINKERCAD [Open](https://www.tinkercad.com/)
	
## Components required
1. Arduino ANO
2. 5 servo motors MG995
3. jumper wirs
4. 5 potentiometer 10 K ohm 
5. bettrey  5 volt
6.breadboard

## Connections
Connection pins:

5V:  Power (red)

Gnd: Ground (black)

13,10,7,5,3 : Digital Signals (orange, yellow, green, blue, purple)

A0,A1,A2,A3,A4 : Analog Signals (violet, brown, grey, cyan,pink)

## Block diagram & simulation
### 1-servo motor rotate 90 degrees . [click here](https://www.tinkercad.com/things/gbPPDKDpC4S-task-12-servo-motor-0-90/editel?sharecode=F5nGzvf_Q4hBc8hK6pDw1buUxTyYmv8P1hEopJZUgGc)
![image](https://user-images.githubusercontent.com/86161046/122844393-4246c500-d30a-11eb-88ef-e9ba7548b123.png)
Figure (1): Servo Motor at initial value (0 degree

After 1 sec
<img width="747" alt="222" src="https://user-images.githubusercontent.com/86161046/122844479-6b675580-d30a-11eb-9088-3a7c59fdae15.png">

Figure (2): Servo Motor at 90 degrees 

#### The Code 
// Include the Servo library 
#include <Servo.h> 

int servoPin = 3;
int servoPin2 = 5;
int servoPin3 = 7;
int servoPin4= 10;
int servoPin5= 13;


 // Create a servo object 
Servo Servo1, Servo2, Servo3, Servo4, Servo5;
void setup() { 
   // We need to attach the servo to the used pin number 
   Servo1.attach(servoPin); 
Servo2.attach(servoPin2);
Servo3.attach(servoPin3); 
Servo4.attach(servoPin4);
Servo5.attach(servoPin5); 
 



}
void loop(){ 
   
   Servo1.write(90); 
   delay(1000); 
  
   Servo2.write(90); 
   delay(1000); 
    
   Servo3.write(90); 
   delay(1000); 

Servo4.write(90); 
   delay(1000); 

Servo5.write(90); 
   delay(1000); 




}
_

### 2-servo motor rotate 90 degrees and back to 0 degree after 2 sec .[click here](https://www.tinkercad.com/things/gbPPDKDpC4S-task-12-servo-motor-0-90/editel?sharecode=F5nGzvf_Q4hBc8hK6pDw1buUxTyYmv8P1hEopJZUgGc)
![1](https://user-images.githubusercontent.com/64277741/122786121-a5116f80-d2bc-11eb-9a95-e5d2b8a3b9ab.PNG)
Figure (3): Servo Motor at initial value (0 degree)

After 2 sec 
![1 2](https://user-images.githubusercontent.com/64277741/122786155-ae9ad780-d2bc-11eb-8f7c-c81f11a682b0.PNG)
Figure (4): Servo Motor at 90 degrees
After 2 sec back to 0 
![1](https://user-images.githubusercontent.com/64277741/122786121-a5116f80-d2bc-11eb-9a95-e5d2b8a3b9ab.PNG)
Figure (5): Servo Motor back from 90 to 0 degree

#### The code 
`#include <Servo.h> 
 
int servoPin = 3;
int servoPin2 = 5;
int servoPin3 = 7;
int servoPin4= 10;
int servoPin5= 13;


 Servo Servo1, Servo2, Servo3, Servo4, Servo5;
void setup() { 
   // We need to attach the servo to the used pin number 
   Servo1.attach(servoPin); 
Servo2.attach(servoPin2);
Servo3.attach(servoPin3); 
Servo4.attach(servoPin4);
Servo5.attach(servoPin5); 
 
}
void loop(){ 
delay(2000); 
  
Servo1.write(90); 
   
Servo2.write(90); 
    
Servo3.write(90); 
   

Servo4.write(90); 


Servo5.write(90); 
  
delay(2000);
  
Servo1.write(0);
Servo2.write(0);
Servo3.write(0);
Servo4.write(0);
Servo5.write(0);




}
`_


### 3- Control multiple servo motors using Potentiometer [click here](https://www.tinkercad.com/things/jBKW8pofJhZ-task-3-control-servo-motor-using-potentiometer/editel?sharecode=FqY5TjQ9On_IY1DgVje0gg_ci8Gl3PQnv6i9iKbzVOA)
At begin
![3](https://user-images.githubusercontent.com/64277741/122786908-75169c00-d2bd-11eb-9624-60cee51a1ea6.PNG)
Figure (6): Five Servo Motor with Five Potentiometers

After start simulation ![4](https://user-images.githubusercontent.com/64277741/122787141-b3ac5680-d2bd-11eb-97f9-08a8c668f9b1.PNG)
Figure (7): Changing the angles of Servo Motors according to change the angles of Potentiometers

#### The Code 
`#include <Servo.h>

Servo s;

Servo t;

Servo u;

Servo v;

Servo w;



int potpin = 0;
int potpin2 = 1;
int potpin3 = 2;
int potpin4 = 3;
int potpin5 = 4;

int val = 0;
int val2 = 0;
int val3 = 0;
int val4 = 0;
int val5 = 0;


void setup()
{

  s.attach(13);  // attaches the servo on pin 13 to the servo object
  t.attach(10);
  u.attach(7);
  v.attach(5);
  w.attach(3);
}

void loop()
{

val = analogRead(potpin);
val = map(val, 3, 1023, 0, 176);

s.write(val);

delay(25);

val2 = analogRead(potpin2);
val2 = map(val2, 0, 1023, 0, 180);

t.write(val2);

delay(25);

val3 = analogRead(potpin3);
val3 = map(val3, 0, 1023, 0, 180);

u.write(val3);

delay(25);

val4 = analogRead(potpin4);
val4 = map(val4, 0, 1023, 0, 180);

v.write(val4);

delay(25);

val5 = analogRead(potpin5);
val5 = map(val5, 0, 1023, 0, 180);

w.write(val5);

delay(25);

}
`_

