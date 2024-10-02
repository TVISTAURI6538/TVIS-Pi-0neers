![Logo of TVIS-PiOneers](Logo.png)
___
**GitHub repository for WRO INDIA Nationals Team TVIS-Pi0neers Future Engineers 2024. It contains our work on building a robot for self-assisted track navigation.**

Below is the documentation of the self-autonomous driving car
___
# Contents
- [Hardware Sketch](#hardware)
  - [Parts Used](#parts-used)
  - [Chassis](#chassis)
  - [Understanding Power and Control](#understanding-power-and-control)
  - [Motors](#motors)
  - [Sensors](#sensors)
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
Our self-driving car consists of an [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#ackerman-steering)  metal chassis and integrates standard components such as cameras, sensors, and electrical systems to optimize motor torque, performance, etc.
[Photo of the overall and completed robot]
 ## Parts Used
- Raspberry Pi 4 Model B
- Arduino Nano
- Web Camera
- Ackerman Steering Metal Chassis 
- 2200MAH 3S 80C  LiPo Battery
- LM2596 Step Down DC-DC Buck Converter Adjustable Module
- TCS-230 Color sensor
- Push Button
- Dual Shaft Plastic Geared Motor
- Lego parts and Wheel Rim (For Elevation)
## Chassis
Our [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) car chassis is designed with a lower base, featuring a Lego component and a sturdy wheel rim to support the upper platform. The upper platform houses a PCB board, where a Raspberry Pi 4 Model B is connected to a camera, an Arduino Nano, and several LEDs that indicate the operational status of the microcontrollers. Additionally, it incorporates a variable converter and a step-down buck converter to ensure efficient power management. Under the lower base, we have integrated a color sensor, which enhances the robot's ability to interact with its environment by detecting specific colors.

We chose a [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) car metal chassis for its precision steering, significantly enhancing our robot's performance. Ideal for high-speed projects, the chassis features an [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) mechanism that mimics real-world vehicle geometry, offering accurate control, especially for automotive simulations. It is designed to handle heavier loads and provides superior stability and control, outperforming traditional skid-steering systems, with a front crash-absorbing construction for durability in demanding environments.
<div align="center">
<img src="Ackerman Steering Chassis.jpg" alt="Ackerman Steering Metal Chassis" width="400" height="400">
</div>
<br>

| Chassis without Alteration | Chassis with Alteration |
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/7d53ea98e56dc66d1b2d5453410f25f88bbe4a76/Chassis%20without%20Alteration.jpg" alt="Image" width="431" height="292"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/3d79248da4fb02d1d307b51a97997534d7b6f35e/Chassis%20with%20Alteration.jpg " alt="Image" width="431" height="292"/> |

We upgraded the motor because of low torque, which improved acceleration and overall performance. This change allows the robot to navigate challenging conditions more easily.

## Understanding Power and Control
The vehicle is powered by a single 2200 mAh 3S LiPo battery, producing 11.1 volts. This voltage is routed through LM2596 step-down DC-DC buck converters and a Buck Converter Module USB Voltage Regulator rated at 5A, efficiently reducing the voltage to safe levels. These converters safeguard the Arduino Nano, Raspberry Pi, and high-torque servo from potential overvoltage damage, ensuring reliable operation and extending the lifespan of all components.

The Arduino Nano is connected to a variable step-down buck converter, which regulates the speed of the steering motors. We fine-tuned the power supplied to the motors to ensure that both their speed and the operation of the sensors were optimized, allowing for accurate vehicle navigation. The Arduino Nano communicates with the motors using PWM (Pulse Width Modulation) pins, enabling precise control of their performance.

<table>
    <tr>
        <th colspan="4">Individual Components</th>
    </tr>
    <tr>
      <td>
           <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/3d8c70f1a72dc9ac5bdda654ed983fac5527c502/2200%20mAh%20Lipo%20Battery.jpg" alt="Image" width="431" height="292"/><br>
            2200 mAh Lipo Battery
        </td>
        <td>
           <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/0417a12bb013ab10ab0c64578d7a6ebe1776d6b2/Arduino%20Nano.jpg" alt="Image" width="431" height="292"/><br>
            Arduino Nano
        </td>
        <td>
             <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/d51f7891a8e87f3b2f734b9ad5d0b60ee02faeea/LM2596%20Buck%20Converter.jpg" alt="Image" width="431" height="292"/><br>
            LM2596 Step Down DC-DC Buck Converter Adjustable Module
        </td>
        <td>
             <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/359e8373da78674313e41fab2dd8878b5f2317e8/USB%20Buck%20Converter.jpg" alt="Image" width="431" height="292"/><br>
            Buck Converter Module 5A USB Voltage Regulator
        </td>
    </tr>
</table>

## Motors

Our car features rear-wheel drive, powered by a plastic gear dual shaft motor and an LD-1501MG, a high-quality servo. The dual shaft motor is controlled through a variable step-down buck converter, providing enhanced control and feedback for more precise performance.

The chassis was initially equipped with a ready-made brushless DC motor that did not meet our torque expectations. As a result, we decided to modify the chassis and install a dual-shaft motor, which significantly enhanced the car's performance.

We opted for servo-based steering because it supports [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) and can operate at higher voltages, enabling us to extract more power from it.

| Motor Modification | Servo and Steering |
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/fee35bc691b07fb0b37f6e46b393c0c5df1b9d9b/Chassis%20with%20Alteration%20Pic.png" alt="Image" width="431" height="292"/> |<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/87c679497f70b1957eaf71e3fe3d9aff04042a1e/Servo%20based%20Steering.png" alt="Image" width="431" height="292"/>|

## Sensors
We have integrated the TCS-230 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) below the chassis to detect the blue and orange lines on the game mat. After careful calibration of the color values, This calibration process involved adjusting the sensitivity levels and thresholds to enhance the sensor's ability to differentiate between the blue and orange colors, allowing the robot to respond effectively to changes.

We initially used the TCS-34725 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) but found it to be inaccurate when tracking fast-paced movements, resulting in unreliable readings. To address this, we switched to the TCS-230 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor), which has proven to be a superior alternative, providing accurate color detection and enhancing our system's responsiveness during rapid maneuvers.

We have equipped the front of the car with a wide-angle camera to detect the corners of black walls and identify red and green blocks, preventing collisions. The camera is securely mounted on the Raspberry Pi case using double tape, which ensures precise distance calculations in the algorithm, enhancing navigation and obstacle detection.

| Color sensor placed below the chassis | Camera mounted on top of the Raspberry Pi Case |
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/197f6f13374c1c13a13e4656a1a5d1e1633b4d48/Color%20sensor%20Attachment%20Pic.png" alt="Image" width="431" height="292"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/12aa34f148e0594feb91c38ac088f3d06b09e6fa/Camera%20mounted%20on%20top%20of%20the%20Raspberry%20Pi%20case.jpg " alt="Image" width="431" height="292"/> |
___
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

We decided to take a unique approach by combining the functionality of the Ultrasonic Sensor with that of the Color sensor and Gyro Sensor. But this also proved to be inaccurate, so we decided to move with the EV3 Mindstorms 

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
We then decided to integrate this gyro sensor and ultrasonic sensor but the ultrasonic sensors gave very inaccurate readings during the robot's run. Therefore, we decided to solve the open challenge by using EV3.

# Demonstration Videos

