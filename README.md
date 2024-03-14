# EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor
###  DATE: 14/03/2024
###  NAME: JAYA SURYAA K
###  ROLL NO : 212222040060
###  DEPARTMENT: CSE
## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 
![image](https://user-images.githubusercontent.com/36288975/166430594-5adb4ca9-5a42-4781-a7e6-7236b3766a85.png)
### CIRCUIT DIAGRAM
![WhatsApp Image 2024-03-14 at 21 34 19_9d981554](https://github.com/KjayasuryaaGkarunagaran/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119476217/e8c617fe-abc7-42dc-b834-ecfa91628032)
### SCHEMATIC VIEW :
![WhatsApp Image 2024-03-14 at 21 28 29_95defb5d](https://github.com/KjayasuryaaGkarunagaran/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119476217/731d3ad0-399c-4463-9d3a-cbf100e292dd)

### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 

int echopin=6;

int trigpin=7;

int red=8;

int green=9;

long duration;

float distance;

void setup()


{

  pinMode(echopin,INPUT);
  
  pinMode(trigpin,OUTPUT);
  
  pinMode(red,OUTPUT);
  
  pinMode(green,OUTPUT);
  
  Serial.begin(9600);
}


void loop()

{

  
  digitalWrite(trigpin,LOW);
  
  delay(10);
  
  digitalWrite(trigpin,HIGH);
  
  delay(10);
  
  digitalWrite(trigpin,LOW);
  
  duration=pulseIn(echopin,HIGH);
  
  distance=duration*0.034/2;
  
  Serial.print("distance=");
  
  Serial.print(distance);
  
  Serial.println("cms");
  
  if(distance<50)
  
  {
  
    digitalWrite(green,HIGH);
    
    delay(500);
    
    digitalWrite(green,LOW);
    
    delay(500);
  }
  
  
  else
  
  { 
  
    digitalWrite(red,HIGH);
    
    delay(500);
    
    digitalWrite(red,LOW);
    
    delay(500);
  }
  
}


### Distance vs measurement table 
![WhatsApp Image 2024-03-14 at 21 34 44_085ddd54](https://github.com/KjayasuryaaGkarunagaran/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119476217/3ec4cd4f-b780-4668-b5ad-4043e98b8242)

                       Average error = sum/ number of readings 
 ### CHART
 ![WhatsApp Image 2024-03-14 at 21 34 19_2689d5c9](https://github.com/KjayasuryaaGkarunagaran/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119476217/63ab0c2f-9acb-437c-b4b8-df87d7a2f42f)
### OUTPUT 
### ON DISTANCE (DISTANCE<50)
![WhatsApp Image 2024-03-14 at 21 41 09_016d04b3](https://github.com/KjayasuryaaGkarunagaran/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119476217/aaa990ab-cf69-47d6-ad96-fcbffd738593)

### ON DISTANCE (DISTANCE>50)
![WhatsApp Image 2024-03-14 at 21 34 19_d9affe02](https://github.com/KjayasuryaaGkarunagaran/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119476217/2cbc6693-da99-4ecb-a1b0-ca3e93f90a35)

### RESULTS



 
