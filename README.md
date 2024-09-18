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
### 3.1. Servo Motor Control Action Through PCA9685 using Joystick
