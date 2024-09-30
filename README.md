![Logo of TVIS-PiOneers](Logo.png)
___
**GitHub repository for WRO INDIA Nationals Team TVIS-Pi0neers Future Engineers 2024. It contains our work on building a robot for self-assisted track navigation.**

Below is the documentation of the self-autonomous driving car
___
# Contents
- [Hardware Sketch](#hardware)
  - [Parts Used](#parts-used)
  - [Chassis](#chassis)
  - [Photos](#photos)
- [Software Sketch](#software)
  - [Programming Language](#programming-language)
  - [Open Challenge](#open-challenge)
     - [Ultrasonic Sensor](#ultrasonic-sensor)
     - [Gyro Sensor](#gyro-sensor)
     - [Color Sensor](#color-sensor)
  - [Obstacle Challenge](#obstacle-challenge)
    - [Improving image processing and predictions through the camera](#improving-image-processing-and-predictions-through-the-camera)
       - [Sensor](#sensor)
       - [Sensor](#sensor)
       - [Sensor](#sensor)
- [Our Team](#our-team)
- [Our Approach](#our-approach)
- [Problems we encountered on the way](#problems-we-encountered-on-the-way)
- [Demonstration Videos](#demonstration-videos)
 ___
 # Hardware
Our self-driving car consists of an [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering)  metal chassis and integrates standard components such as cameras, sensors, and electrical systems to optimize motor torque, performance, etc.
[Photo of the overall and completed robot]
 ## Parts Used
- Raspberry Pi 4 Model B
- Arduino Nano
- Camera
- Ackerman Steering Metal Chassis 
- Three HC-SRO4 Ultrasonic Sensors 
- L298N Motor Driver Module
- 2200 mh battery LIPO
- LM2596 Step Down DC-DC Buck Converter Adjustable Module
- TCS-230 Color sensor
- MPU-6050 Gyro sensor
## Chassis
Our [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) car chassis is designed with a lower base, featuring a Lego component and a sturdy wheel rim to support the upper platform. The upper platform houses a PCB board, where a Raspberry Pi 4 Model B is connected to a camera, an Arduino Nano, and several LEDs that indicate the operational status of the microcontrollers. Additionally, it incorporates a variable converter and a step-down buck converter to ensure efficient power management. Under the lower base, we have integrated a color sensor, which enhances the robot's ability to interact with its environment by detecting specific colors.

We chose a [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) car metal chassis for its precision steering, significantly enhancing our robot's performance. Ideal for high-speed projects, the chassis features an Ackerman steering mechanism that mimics real-world vehicle geometry, offering accurate control, especially for automotive simulations. Designed to handle heavier loads, it provides superior stability and control, outperforming traditional skid-steering systems, with a front crash-absorbing construction for durability in demanding environments. We altered the motor due to low torque, improving acceleration and overall performance, allowing the robot to navigate challenging conditions more efficiently.
<div align="center">
<img src="Ackerman Steering Chassis.jpg" alt="Ackerman Steering Metal Chassis" width="300" height="300">
</div>
<br>

| Chassis without Alteration | Chassis with Alteration |
|:-------------|:--------------:|
|![Chassis without Alteration]()|

## Photos
| Left-aligned | Center-aligned |
|:-------------|:--------------:|
| Row 1, Col 1 | Row 1, Col 2   | 
| Row 2, Col 1 | Row 2, Col 2   | 


# Software 
## Programming Language 
## Open Challenge
### Ultrasonic Sensor
### Gyro Sensor
### Color Sensor
## Obstacle Challenge 
### Improving image processing and predictions through the camera.
#### Sensor
#### Sensor
# Our Team
**Vaishant Ananth** is an 11th-grade student, he aspires to become a robotic engineer passionate about coding and hardware. He is actively involved in various technology challenges and dedicated to mastering both the software and hardware aspects of robotics.

**Ruba Darshan Ashok Kumar** is an 11th-grade student passionate about coding and web design. Experienced in competitive environments, demonstrating strong leadership skills. Aspiring robotic engineer dedicated to excellence in documentation and design. 

We both study at The Velammal International School, Ponneri

We are very thankful to those who helped in completing our project.

Mrs.Anisree-Robotics Coach

Mr.Akash Singh-Robotics Trainer

Mrs.Hemalatha-VKP Techsavy Coordinator

Mr.Manoj-Lab assistant
# Our Approach
In our first attempt to tackle the open challenge, we developed a simple maze-solving algorithm using three ultrasonic sensors. However, we encountered excessive static and backward movement issues in the algorithm.

We decided to take a unique approach by combining the functionality of the Ultrasonic Sensor with that of the Color sensor and Gyro Sensor. but this also proved to be inaccurate, so we decided to move with the EV3 Mindstorms 

# Problems we encountered on the way
We decided to use the TCS-34725 for the color sensor.

<div align="center">
<img src="TCS-34725.jpg" alt="TCS-34725" width="200" height="200">
</div>
<br>
The sensor we initially used proved to be highly inaccurate when tracking fast-paced movement. As a solution, we opted to utilize the TCS-230, which effectively served as a superior alternative to the TCS-34725.
<br><br>
<div align="center">
<img src="TCS-230.jpg" alt="TCS-230" width="200" height="200">
</div>
We then decided to integrate this gyro sensor and ultrasonic sensor but the ultrasonic sensors gave very inaccurate readings during the robot's run. Therefore, we decided to solve the open challenge by using EV3

# Demonstration Videos

