![Logo of TVIS-PiOneers](Logo.png)
___
**GitHub repository for WRO INDIA Nationals Team TVIS-Pi0neers Future Engineers 2024. It contains our work on building a robot for self-assisted track navigation.**

Below is the documentation of the self-autonomous driving car
___
# Contents
- [Hardware Sketch](#hardware)
  - [Parts Used](#parts-used)
  - [Building and Schematic Diagram](#building-and-schematic-diagram)
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
 ## Parts Used
- RC Offroad Car Chassis 
- Arduino Nano
- Three HC-SRO4 Ultrasonic Sensors 
- L298N Motor Driver Module
- 2200 mh battery LIPO
- LM2596 Step Down DC-DC Buck Converter Adjustable Module
- TCS-230 Color sensor
- Gyro sensor
# Building and Schematic Diagram
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
**Vaishant Ananth** As an 11th-grade student, he aspires to become a robotic engineer with a passion for coding and hardware. He is actively involved in various technology challenges and dedicated to mastering both the software and hardware aspects of robotics.

**Ruba Darshan Ashok Kumar** is an 11th-grade student passionate about coding and web design. Experienced in competitive environments, demonstrating strong leadership skills. Aspiring robotic engineer dedicated to excellence in documentation and design. 

We both study at The Velammal International School, Ponneri.

# Our Approach
In our first attempt to tackle the open challenge, we developed a simple maze-solving algorithm using three ultrasonic sensors. However, we encountered issues with excessive static and backward movement in the algorithm.

We decided to take a unique approach by combining the functionality of the Ultrasonic Sensor with that of the Color sensor and Gyro Sensor.
# Problems we encountered on the way
We decided to use the TCS-34725 for the color sensor.

<div align="center">
<img src="TCS-34725.jpg" alt="Placeholder Image" width="200" height="200">
</div>
The sensor we initially used proved to be highly inaccurate when tracking fast-paced movement. As a solution, we opted to utilize the TCS-230, which effectively served as a superior alternative to the TCS-34725.

<div align="center">
<img src="TCS-230.jpg" alt="Placeholder Image" width="200" height="200">
</div>

# Demonstration Video

