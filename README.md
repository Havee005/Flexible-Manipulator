# Flexible-Manipulator
Flexible Manipulator: Bending into the Future of Robotics 🤖

Inspired by nature's most flexible creatures like elephant's trunk and octopuse's tentacles, Continuum Robot brings smooth, 6-DOF bending motion to robotic systems. Unlike rigid, jointed arms, this robot mimics biological movement, offering precise control in 3D space. With a CAD-designed model and integrated soft robotics end-effector, it demonstrates seamless object manipulation and dynamic flexibility.

# 1. Concept
   This model is made by keeping in mind many actions to be performed at a single time. The system is designed such as it has 4 different units combined to work as a single system, they are 

## 1.1. Continuum Arm
<p align="center">
  <img src="https://github.com/user-attachments/assets/cf4fed70-9b71-44e7-a259-cb9fb3aa5d8a">
</p>

* The Continuum Arm has six segments, each 70 mm long.
* Joints are formed by combining two segments, with each joint controlled by two bending wires.
* Segments are 3D-printed using Polylactic Acid (PLA).
* Tendons are made from thin steel threads.
* Threaded discs connect the segments, allowing wires to pass through and slide between them.
* The segments bend as the connective discs move in different directions, without changing their length.

## 1.2. Driving Box

* The robot's architecture consists of 12 wires controlling the 6 continuum segments.
* Each of the 6 servo motors in the driving box controls one segment, with 2 tendons attached to each segment.
* A pulley mechanism powered by the servo motors moves the tendons in a straight line.
* The driving box is divided into two halves:
  * The first half houses the motor unit.
  * The second half controls the servos via drivers.

## 1.3. Processing

* The Arduino Uno microcontroller serves as the system's processing unit.
* It communicates with the servo controller (PCA9685) via the I2C (Inter-Integrated Circuit) protocol.
* This communication requires only two wires between the master and slave boards but can control up to 16 individual servos simultaneously.
* Two key connections:
  * Serial Data (SDA): Used for sending and receiving data between multiple masters and slaves.
  * Serial Clock (SCL): Carries clock signals for synchronization.
 
## 1.4. Soft Arm
* The end effector is designed for lifting fragile and brittle objects.
* It is manufactured by pouring two different liquid silicone rubber (LSR) solutions into a 3D-printed mold.
* The silicone mold cures in 6 hours, after which it's ready for use.

# 2. Working
<p align="center">
  <img src="https://github.com/user-attachments/assets/97b45238-7c25-4b84-9f0f-1fc3e6fcdee7">
</p>

* The joystick provides input signals to control both the continuum arm and the soft actuators.
* The microcontroller (Arduino Uno), which is the brain of the system, receives input from the joystick to control the entire robot.
* The Arduino Uno uses the I2C protocol to communicate with the PCA9685 servo controller, which sends PWM signals to the servo motors to achieve the desired angles.
* The soft robot end-effectors of the continuum arm are actuated via signals from a switch through the microcontroller.
* The Arduino Uno acts as the master controlling the PWM controller (slave), using only two wires for communication.
* The servo motors move the continuum arm to the desired angle in all directions.

## 2.1. Component Description

| Components | Working Parameters |
| :----: | :----: |
| Arduino UNO | <ul><li>Operating Voltage - 5 to 12V</li><li>Clock Speed - 16Mhz</li><li>Microprocessor - ATMega328P</li></ul> | 
| PWM Servoo Controller (PCA9685) |<ul><li>Operating Voltage – 6V</li><li>Servo Controlled - 16 Individual servos</li></ul> |
| Servo Motor (MG995)| <ul><li>Operating Voltage – 4.8V to 6V</li><li>Stall Torque - 9 kg/cm</li><li>Gear - Metal</li></ul> |
| Liquid Silicone Rubber | <ul><li>Part No. - 110</li><li>Curing Time - 6 hours</li><li>Mixing Proportion - 1:1</li></ul> |
| Compressor Machine | <ul><li>Operating Voltage – 12V</li></ul> |
| Power Supply | <ul><li>Parameter - 350 W SMPS</li></ul> |

# 3. Result

### 3.1. Continuum Single Segment Action
[![Single Segment](https://github.com/user-attachments/assets/thumbnail.jpg)
](https://github.com/user-attachments/assets/a7f8f5ff-005b-416e-a2ee-82453f930020)

### 3.2. Servo Motor Control Action Through PCA9685 using Joystick
[![servo video](https://github.com/user-attachments/assets/thumbnail.jpg)
](https://github.com/user-attachments/assets/f3ba16c5-ed57-46d7-b09f-91d38812cedd)

### 3.3. Continuum Assembly
<p align="center">
  <img src="https://github.com/user-attachments/assets/c60f777f-d809-4c78-bcb2-97c6e3cd6ca9">
</p>

### 3.4. Soft Robot Mold
<p align="center">
  <img src="https://github.com/user-attachments/assets/ee5ad736-33b7-4361-a786-0593e2085cc0">
</p>

### 3.5. Soft Gripper Working Demo with Simple Syringe (Pneunet)
[![Soft Gripper](https://github.com/user-attachments/assets/thumbnail.jpg)
](https://github.com/user-attachments/assets/5b54fa6e-752b-4356-8e0c-c6d8558aac59)

### 3.6. [Flexible Manipulator &  Working Model](https://www.linkedin.com/feed/update/urn:li:activity:6935610456023670784?updateEntityUrn=urn%3Ali%3Afs_updateV2%3A%28urn%3Ali%3Aactivity%3A6935610456023670784%2CFEED_DETAIL%2CEMPTY%2CDEFAULT%2Cfalse%29&originTrackingId=39M59SDBQvWf5QQ07EeXqA%3D%3D&lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_recent_activity_content_view%3Bkf68yQNBSuKK%2F4YOQBOxdg%3D%3D)
<p align="center">
  <img src="https://github.com/user-attachments/assets/c4fcd13c-7cb3-4ac2-af1c-b0be00811ab6">
</p>

# 4. References
- G. Robinson, J.B.C. Davies, “Continuum Robots - A State of the Art,” IEEE Conf. on Robotics and Automation, pp. 2849-2854, 1999.
- G. Robinson and J. B. C. Davies, “Continuum robots ‐ a state of the art,” Proceedings of IEEE International Conference on Robotics and Automation, Detroit, Michigan, May 1999, vol. 4, pp. 2849‐2854.
- W. Wang, W. Yu and H. Zhang, “JL‐2: A Mobile Multi‐robot System with Docking and Manipulating Capabilities,” International Journal of Advanced Robotic Systems, 2010, vol. 7, no. 1, pp. 9‐18.
- S. M. Rezaei, F. Barazandeh, M. S. Haidarzadeh, and S. M. Sadat, “The effect of snake muscular system on actuators’ torque,” Journal of Intelligent and Robotic Systems, 2010, vol.59, no.3, pp.299‐318.
- J. Casper and R. R. Murphy, “Human‐robot interactions during the robot‐assisted urban search and rescue response at the World Trade Center,” IEEE Transactions on Systems, Man, and Cybernetics, 2003, vol. 33, no. 3, pp. 367‐385.
- H. Zhang, W. Wang, Z. Deng, G. Zong and J. Zhang, “A novel reconfigurable robot for urban search and rescue,” International Journal of Advanced Robotic Systems, 2006, vol. 3, no. 4, pp. 359‐366.
- A. Ghanbari and S. Noorani, “Optimal trajectory planning for design of a crawling gait in a robot using genetic algorithm,” International Journal of Advanced Robotic Systems, 2011, vol. 8, no. 1, pp. 29‐36.
- N. Simaan, “Snake‐like units using flexible backbones and actuation redundancy for enhanced miniaturization,” Proceedings of IEEE International Conference on Robotics and Automation, Barcelona, Spain, April 2005, pp. 3023‐3028.
- K. Xu and N. Simaan, ʺAn Investigation of the Intrinsic Force Sensing Capabilities of Continuum Robots,ʺ IEEE Transactions on Robotics, 2008, vol.24, no.3, pp.576‐587.
- K. Xu and N. Simaan, “Intrinsic wrench estimation and its performance index for Multisegment continuum robots,” IEEE Transactions on Robotics, 2010, vol. 26, no. 3, pp. 555–561.
- B. A. Jones and I. D. Walker, “Kinematics for multisection continuum robots,” IEEE Transactions on Robot, 2006, vol. 22, no. 1, pp. 43‐55.

