# ANDROID CONTROLLED PICK & PLACE ROBOT 
# (A HELPING HAND)
Things carries Android controlled robot can be used to pass on the things to one another easily by using our android mobile. This robot can be used in schools or places where lots of physically disabled people study or work.

![image](https://user-images.githubusercontent.com/37563886/70070156-20e39280-1619-11ea-8a0a-1f1e14470c9d.png)


# INTRODUCTION

Things carries Android controlled robot can be used to pass on the things to one another easily by using our android mobile. This robot can be used in schools or places where lots of physically disabled people study or work.
In making this carrier robot AVR Atmega 32 micro controller is being to control all its features and functioning.
And this robot can be modified in many ways such as –
It can be converted into a pick and place robot easily by just attaching the robotic arm in the front which consist of one servo and DC motor (60 rpm) for its controlling. This robot can be prepared under the cost of Rs.2500/- for both the application.
USE FOR PHYSICALLY DISABLED PEOPLE-
This robot will ease the work of many physically challenged people as if this robot is made on a large scale then physically disabled people will easily pick up the things which they use in their daily life.
If by removing the carrier tray we fix the robotic arm then the robot will be ready for its another application that is pic and place which can be used to pick the small things.

# USE FOR PHYSICALLY DISABLED PEOPLE

This robot will ease the work of many physically challenged people as if this robot is made on a large scale then physically disabled people will easily pick up the things which they use in their daily life.
If by removing the carrier tray we fix the robotic arm then the robot will be ready for its another application that is pic and place which can be used to pick the small things.


# CIRCUIT DIAGRAM EXPLAINATION

![image](https://user-images.githubusercontent.com/37563886/70070671-ff36db00-1619-11ea-9687-b2a433dc9f7d.png)

AVR micro controller consist of 32 GPIO’s and it is 8 bit architecture consist of 4 Port registers named PORTA, PORTB, PORTC, PORTD.
And to make any of the pin output from any PORT we have to program their respective data registers named as DDRA, DDRB, DDRC, DDRD . 
In this robot on PORTA all the 4 motor are placed by attaching motor drivers (L293D) between pins and motors which will ensure the movement of the robot.
0th and 1st pin of PORTD are made output for the reception and transmission of the commands through Bluetooth and in the schematic diagram instead of Bluetooth we have used the virtual terminal which will do the same work.
And if want to attach robotic arm also then for we have generated PWM on the 5th pin of PORTD by using TIMER1 of the controller which is 18 bit timer and can accept the maximum value of 65535.

# COMPONENTS OF THE ROBOT

**If we want to use wi-fi instead of Bluetooth for giving command from the mobile then we can use server of www.thingspeak.com which is providing free server channels to the people. 

This robot consist these components as its parts-
1.	4 DC motor (100 rpm).
2.	1 12V DC battery.
3.	1 AVR Atmega 32 development board.
4.	Atmega 32 controller IC.
5.	Chassis.
6.	1 servo motor and 1 DC motor of 60rpm to be used for pick and place robot).
a.	Robotic arm-gripper.
7.	4 tyres.
8.	Bluetooth (HC-05 or HC-06)
9.	Wi-fi module ESP8266 (for larger range)
10.	Motor driver (L293D)

**And the app we will use is named BLUETOOTH CONTROLLER in which we can set the keys in whatever way we want and it is easily available on Play Store.
