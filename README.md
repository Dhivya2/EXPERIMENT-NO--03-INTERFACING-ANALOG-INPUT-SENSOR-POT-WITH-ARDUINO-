EXPERIMENT-NO--03-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-

AIM: To interface a Analog input (angular displacement sensor POT) and scale the values up on change in the input.

COMPONENTS REQUIRED:

10 KΩPOT

1 KΩ resistor

Arduino Uno

USB Interfacing cable

Connecting wires

LED of choice

**THEORY:

Analog signals:

Analog signals – directly measurable quantities in terms of some other quantity.

Examples:

Thermometer – mercury height rises as temperature rises
Car Speedometer – Needle moves farther right as you accelerate
Stereo – Volume increases as you turn the knob Reason for conversion of analog to digital quantity is that as the controller or any microprocessor works with digital signals in the form of 0 and 1s, in order to make the signal compatible most of the analog signals are converted into its equivalent digital level signals using an analog to digital converter . Quantizing - breaking down analog value is a set of finite states Encoding - assigning a digital word or number to each state and matching it to the input signal There are two ways to best improve accuracy of A/D conversion: Increasing the resolution which improves the accuracy in measuring the amplitude of the analog signal. Increasing the sampling rate which increases the maximum frequency that can be measured. General specifications of analog sensor  1. Range  2. Accuracy  3.Linearity  4.Compatiblity  5. signal conversion capability
Potentiometer A potentiometer, informally a pot, is a three-terminal resistor with a sliding or rotating contact that forms an adjustable voltage divider. If only two terminals are used, one end and the wiper, it acts as a variable resistor or rheostat. Potentiometers are commonly used to control electrical devices such as volume controls on audio equipment. Potentiometers operated by a mechanism can be used as position transducers, for example, in a joystick. Potentiometers are rarely used to directly control significant power (more than a watt), since the power dissipated in the potentiometer would be comparable to the power in the controlled load 

CIRCUIT DIAGRAM

![image](https://user-images.githubusercontent.com/89122599/172778362-105ff22b-900f-434c-8480-38dd447ce072.png)


**FIGURE -01

PROCEDURE:

Connect the circuit as per the circuit diagram
Connect the board to your computer via the USB cable.
If needed, install the drivers.
Launch the Arduino IDE.
Select your board (If you the board is arduino uno, select accordingly).
Select your serial port, accordingly ( E.g. COM5 )
Open the file of the program and verify the error , clear if any errors that are existing
Upload the program and check for the physical working.
Ensure safety before powering up the device

PROGRAM

void setup()


{

 pinMode(A0, INPUT);
 
 pinMode(7, OUTPUT);
 
 pinMode(8, OUTPUT);
 
 Serial.begin(9600);
 
 
}

void loop()

{

 int Sensorvalue = analogRead(A0);
 
 //Serial.print("Sensor Value = ");
 
 Serial.println(Sensorvalue);
 
 //delay(500);
 
 if(Sensorvalue<=30)
 
 {
 
   digitalWrite(8, HIGH);
   
   digitalWrite(7, LOW);
   
 }
 
 else if(Sensorvalue>=500)
 
 {
 
   digitalWrite(8,LOW);
   
   digitalWrite(7,HIGH);
   
 }
 
}


** Simulation output

![image](https://user-images.githubusercontent.com/89122599/172778448-dee73787-32d6-489c-8464-0e3758b61a23.png)


**FIGURE 02 **

![image](https://user-images.githubusercontent.com/89122599/172778510-d4ec2c0f-7785-454d-8082-a6833f8467ac.png)


**FIGURE 03 **

**RESULT:**

  Arduino uno analog input functioning is learned and interfaced with digital input switch 
