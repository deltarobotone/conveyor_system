# Welcome robot friends! 

This is an additional system for Delta-Robot One. It is called conveyor system. Things for example metal chips can be transported into the robots workingspace to grasp and sort them in different areas. The conveyor system extents the Delta-Robot One project and provides the posability to do some new tasks. Be creative and do some cool things with it. In the future it is planned to extend the robot and conveyor system with an image processing platform based on a Raspberry Pi 3 board. 

This repository provides all parts you need to build the conveyor system. Delta-Robot One and also this system are mainly designed for students and makers with an educational thought. The Conveyor System for Delta-Robot One is designed as a kit. The pluggable mechanical solution make the assembly fast and easy. Like Delta-Robot One this system is basicly build of lasercutted and 3D-printed parts. An introduction at the containing wiki provides a description of all parts including production files, drawings and a list where you can get the parts. If all the parts are produced and/or delivered the assembly steps will be described at the wiki page. The last step decribes the usage of the system with Delta-Robot One. 

With the help of a community (this means you) it could be a world wide educational project. Working on this project is a lot of fun. Learning something about the different topics and share it with the world is realy great. Be part of it...

This video clip show a Delta-Robot One with long pillars found at [hardware parts](https://github.com/deltarobotone/hardware_parts/tree/master/3D_Print/Package) and the Conveyor System.

[<img src="http://img.youtube.com/vi/MGw2fCCIe-g/0.jpg" width="700">](https://www.youtube.com/watch?v=MGw2fCCIe-g)

We used a system like this to grasp some chips at the image processing lab of our university. We detect the chips, the colour and the velocity. In the video above you can see a simple system with no image processing. The chip is only detected by a time of flight sensor. The motor of the conveyor system and the sensor are both connected to the robots interface. This shows the possibility to extend your robot.

There are interfaces provided for:

- Gripper/GND (ON/OFF)
- Motor/GND (PWM max. 4A)
- I2C Bus (SCL/SDA)
- Power/GND (5V/max. 4A)

# Direct link -> [**>>>conveyor_system wiki<<<**](https://github.com/deltarobotone/conveyor_system/wiki)

# What is Delta-Robot One?



# Hardware interface of Delta-Robot One

Delta-Robot One has an hardware interface on it's circuit board to use the conveyor system without any additional hardware like a motordriver or a power supply.

# Conveyor System and Arduino Library

The Arduino Library for Delta-Robot One contains the code which provides the control of an external DC-Motor. So it is possible to use the conveyor system directl. If you would like to go more into detail you can do this without any problem because the software is open source.

Sourcecode: [>>>One System Library<<<](https://github.com/deltarobotone/one_system_library)

The following lines are showing the external motor example of the One System Library. Select this example at Arduino IDE to do the first steps with Delta-Robot One an the Conveyor System.

```c
//Create the DeltaRobotOne-Object
DeltaRobotOne robot(0, 0, 0, 0, 0, 0, 0x27);
void setup()
{ 
//Robot setup
robot.setup(); 
//Power main circuit
robot.power.mainOn();
//Move the robot to the home position (X=0.0,Y=0.0,Z=85.0)  
robot.move.ptp(home);
//Clear the display
robot.display.clear();
//Print out some information on display
robot.display.printLine1(F("External Motor"));
//Wait for 2 seconds
robot.functions.waitFor(2000);
}
void loop()
{
//This example shows you how to use an external motor on the robot interface
//Connect a DC-Motor to interface pins M+ (5V max) and M- (Ground)
//The motor speed can be set beetween 1 and 255
//Set a high motor speed
int speedValue = 255;
//Start the motor
// if you have a high motorspeed you can use this function in this way
robot.extmotor.start(speedValue);
//Wait for 2 seconds
robot.functions.waitFor(2000);
//Stop the motor
robot.extmotor.stop();
//Wait for 2 seconds
robot.functions.waitFor(2000);
//Set a slow motor speed
speedValue = 50;
//If you have a slow motorspeed you can use the startup parameter 
//to set a high speed for 500 milliseconds to start the motor
//Start the motor with startup function
robot.extmotor.start(speedValue,true);
//Wait for 2 seconds
robot.functions.waitFor(2000);
//Set a normal motor speed
speedValue = 150;
//Change the speed of the motor while the motor is running
robot.extmotor.setSpeed(speedValue);
//Wait for 2 seconds
robot.functions.waitFor(2000);
//Stop the motor
robot.extmotor.stop();
//Wait for 2 seconds
robot.functions.waitFor(2000);
}
```

# Python package (One-Easy-Protocol)

A Python package provides the communication protocol with a high level interface to control Delta-Robot One from other systems. So you can control the robot and/or the Conveyor System easily from a system like a Raspberry Pi via USB. Use python package manager to install one-easy-protocol on your system:

Python 2 -> ***pip install one-easy-protocol***

Python 3 -> ***pip3 install one-easy-protocol***

Sourcecode, Tutorials and Documentation of One Easy Protocol:

[>>>One Easy Protocol Python<<<](https://github.com/deltarobotone/one-easy-protocol)

For C++ version of One Easy Protocol have a look at:

[>>>One Easy Protocol C++<<<](https://github.com/deltarobotone/one_easy_protocol)

# Conveyor System assembly

The Conveyor System for Delta-Robot One is designed as a kit. The pluggable mechanical solution make the assembly fast and easy. Choose the colours of some parts to give the system an individual look. All in all building this system provides you with a short practical, educational and interesting experience. Now it‘s time to build your own conveyor system!

***How to build your conveyor?*** No worrys we create a wiki...

Wiki: [>>>conveyor_system wiki<<<](https://github.com/deltarobotone/conveyor_system/wiki)

[<img src="https://raw.githubusercontent.com/deltarobotone/image_database/master/delta_robot_one/delta_robot_one%20(36).jpg" width="500">](https://raw.githubusercontent.com/deltarobotone/image_database/master/delta_robot_one/delta_robot_one%20(36).jpg)

# Conveyor System assembly video clip

[<img src="http://img.youtube.com/vi/3GcX2WYTDjQ/0.jpg" width="500">](https://www.youtube.com/watch?v=3GcX2WYTDjQ)

# Lassercutting Parts

[>>>Documentation<<<](https://github.com/deltarobotone/conveyor_system/wiki/Step-2:-Check-your-parts)

[>>>Files<<<](https://github.com/deltarobotone/conveyor_system/tree/master/Lasercut)

***How to get the layers?*** There are many ways...

- You can use a lasercutter in a Techshop/Makerspace or your School/University
- We ordered from [cutcraft](http://cutcraft.de/) a few times so we can recommend this service
- We don't try it but with a 3D-Printer it has to be possible to create the layers too

[<img src="https://raw.githubusercontent.com/deltarobotone/image_database/master/layers_colors/layers_colors%20(7).PNG" width="500">](https://raw.githubusercontent.com/deltarobotone/image_database/master/layers_colors/layers_colors%20(7).PNG)

Be creative and choose your own design to build an individual robot. Make the world of robots more colourful...

All drawings of the layer system are availible...

[>>>Drawings<<<](https://github.com/deltarobotone/hardware_parts/wiki/Layers-Drawings)

[<img src="https://github.com/deltarobotone/image_database/blob/master/layers_drawings/layers_drawings%20(1).png" width="500">](https://raw.githubusercontent.com/deltarobotone/image_database/master/layers_drawings/layers_drawings%20(1).png)

# Electronics

[>>>Partlist<<<](https://github.com/deltarobotone/conveyor_system/wiki/Step-2:-Check-your-parts)

***How to get the parts?*** All of this are standard parts...

- You can check your own maker stock first ;)
- Use the partlist on the link above and check the recommended shops
- A lot of shops and maybe your school or university have this parts availible

All Schematics are availible also in a fritzing version...

[>>>Schematics<<<](https://github.com/deltarobotone/hardware_parts/wiki/Circuitboard-Schematics)

[<img src="https://github.com/deltarobotone/image_database/blob/master/circuit_board_schematics/circuit_board_schematics%20(4).png" width="500">](https://raw.githubusercontent.com/deltarobotone/image_database/master/circuit_board_schematics/circuit_board_schematics%20(4).png)

# Mechanics

[>>>Documentation<<<](https://github.com/deltarobotone/conveyor_system/wiki/Step-2:-Check-your-parts)

[>>>Files<<<](https://github.com/deltarobotone/hardware_parts/tree/master/3D_Print)

***How to get the parts?*** No problem...

...we tested [i.materialise.com](http://i.materialise.com/) and created some shop items so you can easily order the required parts using this links:

[>>>Drum<<<](https://i.materialise.com/de/shop/item/one-kinematics-package)

[>>>Drum Drive<<<](https://i.materialise.com/de/shop/item/one-kinematics-package)

[>>>Pillar Long Package<<<](https://i.materialise.com/de/shop/item/pillar-package)

[<img src="https://raw.githubusercontent.com/deltarobotone/image_database/master/mechanic_parts/mechanic_parts%20(7).PNG" width="500">](https://raw.githubusercontent.com/deltarobotone/image_database/master/mechanic_parts/mechanic_parts%20(7).PNG)

All drawings of the mechanics are availible...

[>>>Drawings<<<](https://github.com/deltarobotone/hardware_parts/wiki/Mechanic-Drawings)

[<img src="https://github.com/deltarobotone/image_database/blob/master/mechanic_drawings/mechanic_drawings%20(1).png" width="500">](https://raw.githubusercontent.com/deltarobotone/image_database/master/mechanic_drawings/mechanic_drawings%20(1).png)

# Copyright Notice

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
