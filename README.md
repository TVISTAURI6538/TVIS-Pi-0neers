![Logo of TVIS-PiOneers](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/1838a45001ecb06673d1ae47b39eb53f2fcf61a1/Photos/Logo.png)
___
**GitHub repository for WRO INDIA Nationals Team TVIS-Pi0neers Future Engineers 2024. It contains our work on building a robot for self-assisted track navigation.**

Below is the documentation of the self-autonomous driving car
___
# Contents
- [**Hardware Sketch**](#hardware)
  - [Parts Used](#parts-used)
  - [Chassis](#chassis)
  - [Understanding Power and Control](#understanding-power-and-control)
  - [Motors](#motors)
  - [Sensors](#sensors)
- [**Wiring Diagram**](#wiring-diagram)
- [**Photos**](#photos)
- [**In Depth Algorithm Explanation**](#in-depth-algorithm-explanation)
  - [Wall Avoidance](#wall-avoidance)
  - [Traffic Sign Identification](#traffic-sign-identification)
  - [Lap Count](#lap-count)
  - [Movement](#movement)
  - [Feedback Mechnaism](#feedback-mechanism)
- [**Code and Pseudocode Overview**](#code-and-pseudocode-overview)
- [**Our Team**](#our-team)
- [**Our Journey**](#our-journey)
  - [Problems Encountered On The Way](#problems-encountered-on-the-way)
    - [Problems Faced During Wall Avoidance](#problems-faced-during-wall-avoidance)
    - [Problems Faced During Traffic Sign Identification](#problems-faced-during-traffic-sign-identification)
    - [Problems Faced During Lap Count](#problems-faced-during-lap-count)
    - [Problems Faced During the Feedback Mechanism](#problems-faced-during-the-feedback-mechanism)
- [**Demonstration Videos**](#demonstration-videos)
 ___
 # Hardware
Our self-driving car consists of an [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#ackerman-steering) metal chassis and integrates standard components such as cameras, sensors, and electrical systems to optimize motor torque, performance, etc.
<div align="center">
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/d04ce6644067cbafa35ce97b18eb30ff2151ffca/V-Photos/Bumble%20B%20Cover%20Pic.jpg" alt="Overall Robot" width="700" height="700">
</div>
<br>

 ## Parts Used
- Raspberry Pi 4 Model B
- Arduino Nano
- Web Camera
- Ackerman Steering Metal Chassis 
- 2200MAH 3S 80C  LiPo Battery
- LM2596 Step Down DC-DC Buck Converter Adjustable Module
- TCS-230 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor)
- Push Button
- Dual Shaft Plastic Geared Motor
- Lego parts and Wheel Rim (For Elevation)
## Chassis
Our [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) car chassis is designed with a lower base, featuring a Lego component and a sturdy wheel rim to support the upper platform. The upper platform houses a PCB board, where a Raspberry Pi 4 Model B is connected to a camera, an Arduino Nano, and several LEDs that indicate the operational status of the microcontrollers. Additionally, it incorporates a variable converter and a step-down buck converter to ensure efficient power management. Under the lower base, we have integrated a [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor), which enhances the robot's ability to interact with its environment by detecting specific colors.

We chose a [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) car metal chassis for its precision steering, significantly enhancing our robot's performance. Ideal for high-speed projects, the chassis features an [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) mechanism that mimics real-world vehicle geometry, offering accurate control, especially for automotive simulations. It is designed to handle heavier loads and provides superior stability and control, outperforming traditional skid-steering systems, with a front crash-absorbing construction for durability in demanding environments.
<div align="center">
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/50c2ba68a9a6ea608d6f43ca7d0acce09318adeb/Photos/Ackerman%20Steering%20Chassis.jpg" alt="Ackerman Steering Metal Chassis" width="400" height="400">
</div>
<br>

| Chassis without Alteration | Chassis with Alteration |
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/7d53ea98e56dc66d1b2d5453410f25f88bbe4a76/Chassis%20without%20Alteration.jpg" alt="Image" width="431" height="292"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/3d79248da4fb02d1d307b51a97997534d7b6f35e/Chassis%20with%20Alteration.jpg " alt="Image" width="431" height="292"/> |

We upgraded the motor because of low torque, which improved acceleration and overall performance. This change allows the robot to navigate challenging conditions more easily.

## Understanding Power and Control
The vehicle is powered by a single 2200 mAh 3S LiPo battery, producing 11.1 volts. This voltage is routed through LM2596 step-down DC-DC buck converters and a Buck Converter Module USB Voltage Regulator rated at 5A, efficiently reducing the voltage to safe levels. These converters safeguard the Arduino Nano, Raspberry Pi, and high-torque [servo](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#servo-motor) from potential overvoltage damage, ensuring reliable operation and extending the lifespan of all components.

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

"Our car features a rear-wheel drive system powered by a plastic gear dual shaft motor and an LD-1501MG high-quality [servo](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#servo-motor).. The dual shaft motor is precisely controlled through a combination of a variable step-down buck converter and an L293D motor driver, providing enhanced control and feedback for improved performance and maneuverability."

The chassis was initially equipped with a ready-made 12v gear motor that did not meet our torque expectations. As a result, we decided to modify the chassis and install a dual-shaft motor, which significantly enhanced the car's performance.

We opted for [servo](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#servo-motor)-based steering because it supports [Ackerman Steering](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#steering) and can operate at higher voltages, enabling us to extract more power from it.

| Motor Modification | [servo](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#servo-motor) and Steering | L293D Motor Driver | 
|:-------------:|:--------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/fee35bc691b07fb0b37f6e46b393c0c5df1b9d9b/Chassis%20with%20Alteration%20Pic.png" alt="Image" width="431" height="292"/> |<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/87c679497f70b1957eaf71e3fe3d9aff04042a1e/Servo%20based%20Steering.png" alt="Image" width="431" height="292"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/7d8a22f8fafa1943d3d45af84985f3293b4d6ab3/L293D%20Motor%20Driver.jpg" alt="L293D Motor Driver" width="431" height="292"/>|

## Sensors
We have integrated the TCS-230 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) below the chassis to detect the blue and orange lines on the game mat. After calibrating the color values, This process involved adjusting the sensitivity levels and thresholds to enhance the sensor's ability to differentiate between the blue and orange colors, allowing the robot to respond effectively to changes.

We initially used the TCS-34725 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) but found it to be inaccurate when tracking fast-paced movements, resulting in unreliable readings. To address this, we switched to the TCS-230 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor), which has proven to be a superior alternative, providing accurate color detection and enhancing our system's responsiveness during rapid maneuvers.

We have equipped the front of the car with a wide-angle camera to detect the corners of black walls and identify red and green blocks, preventing collisions. The camera is securely mounted on the Raspberry Pi case using double tape, which ensures precise distance calculations in the algorithm, enhancing navigation and obstacle detection.

| [Color Sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) placed below the chassis | Camera mounted on top of the Raspberry Pi Case |
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/197f6f13374c1c13a13e4656a1a5d1e1633b4d48/Color%20sensor%20Attachment%20Pic.png" alt="Image" width="431" height="292"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/12aa34f148e0594feb91c38ac088f3d06b09e6fa/Camera%20mounted%20on%20top%20of%20the%20Raspberry%20Pi%20case.jpg " alt="Image" width="431" height="292"/> |

___
## Wiring Diagram
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/ae7cb27951d7d5ba86243a4421924a280af31580/Wiring%20Diagram.png" alt="Image" width="1000" height="600"/>

___
# Photos
(Click on the photos to view them in a larger size.)
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/f895f5b59b883f9c397050a92661ed500ccb63f2/Bumble%20B%20Front.jpg " alt="Image" width="431" height="400"/>| <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/9b13e4e1826c967ac8d9e286e4ea64abec91dd87/Bumble%20B%20Back.jpg" alt="Image" width="431" height="400"/>| 
| -------- | -------- |
| <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/9b13e4e1826c967ac8d9e286e4ea64abec91dd87/Bumble%20B%20L_Side.jpg" alt="Image" width="431" height="340"/>  |<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/9b13e4e1826c967ac8d9e286e4ea64abec91dd87/Bumble%20B%20R_Side.jpg" alt="Image" width="431" height="340"/>| 
| <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/9b13e4e1826c967ac8d9e286e4ea64abec91dd87/Bumble%20B%20Top.jpg" alt="Image" width="431" height="400"/> | <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/9b13e4e1826c967ac8d9e286e4ea64abec91dd87/Bumble%20B%20Bottom.jpg" alt="Image" width="431" height="400"/> | 
___
# In Depth Algorithm Explanation
There are mainly 5 aspects on which our Bumble B is based on 
- **Wall Avoidance**
- **Traffic Sign Identification**
- **Lap Count**
- **Movement**
- **Feedback Mechanism**

## Wall Avoidance 
- We decided to use a camera and Raspberry Pi to tackle the wall avoidance task.
  
- We took advantage of the black color of the walls rather than calculating distance. To achieve this, we used the OpenCV library to successfully avoid the black walls.
  
- First, we calibrated the system by defining upper and lower HSV (Hue, Saturation, Value) values for black wall detection.

- Next, we defined a fixed horizontal line below the center of the camera frame using the ```cv2.line``` function. This line served as a reference point for wall detection.
  
- The wall avoidance logic was programmed such that when any black mask comes into contact with the right side of the line, the robot will turn left; if any black mask comes into contact with the left side of the horizontal line, the robot will turn right.
  
- This logic effectively enabled us to avoid black walls successfully.

## Traffic Sign Identification
For effective traffic sign identification, we utilized a Raspberry Pi and a camera, implementing a systematic approach to detect and navigate around red and green traffic signs.

- **Task Overview**: Use a Raspberry Pi and camera to identify traffic signs.

- **HSV Calibration**: Define upper and lower HSV values for red and green traffic signs, applying masking and contouring techniques to isolate them.

- **Bounding Rectangles**: Employ the ```cv2.boundingRect``` function to create bounding rectangles for visualizing the detected traffic signs.

- **Frame Division**:
  - Define two fixed margins to create three zones (left, middle, right) for accurate steering past the signs.
  - This segmentation allows the robot to adjust its turning based on the sign's position.
  
- **Turning Logic**:
  - If the red traffic sign is detected in the middle or right zone, the robot turns right until the sign moves into the left zone (desired zone).
  - If the green traffic sign is detected in the middle or left zone, the robot turns left until it moves into the right zone (desired zone).

| Red Traffic Sign Identification | Green Traffic Sign Identification |
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/5f5d565ff3d284695875cae980f7bd278db93bfa/rasp1.png" alt="Red Traffic Sign Identification" width="431" height="292"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/5f5d565ff3d284695875cae980f7bd278db93bfa/rasp2.png" alt="Green Traffic Sign Identification" width="431" height="292"/> |

- **Logic Resumption**: Once the traffic sign is in the desired zone, the robot resumes wall avoidance logic, prioritizing traffic sign detection.

- **Noise Filtering**: To mitigate the detection of small red and green objects due to reflections on the mat, a minimum size threshold for the bounding rectangles is established.

- **Simultaneous Detection Handling**: When both red and green signs are detected simultaneously, compare their bounding rectangles and prioritize the larger one (indicating the closer traffic sign).

## Lap Count 
For tracking laps, we utilized a TCS-230 [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) controlled by an Arduino Nano, which is mounted on the underside of the chassis. The sensor was calibrated to effectively distinguish between blue, orange, and white colors, allowing for accurate detection of the track’s markings.

We leveraged the blue and orange lines present at the corner sections of the track. When the [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor) detects orange, the robot temporarily halts color detection for 3 seconds using the ```millis()``` function. During this pause, the robot turns right for 1 second before resuming its wall and traffic sign avoidance routines. A similar process occurs when blue is detected, but in this case, the robot turns left instead of right.

To count the laps, we initialized a variable ```i = 0``` to keep track of the number of laps completed. Each time a color is detected, the variable increments by a factor of 1. Once ```i``` reaches 12 (indicating that 3 laps have been completed), the code executes an additional 3-second run before stopping the robot at the same section where it started.

## Movement
- **Propulsion and Steering**: The robot is propelled by a high-torque dual shaft motor and steered using a [servo](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#servo-motor) motor connected to an Ackerman steering mechanism.

- **Dynamic Control**: Functions for forward movement, ```leftTurn```, ```rightTurn```, and ```stopCar``` are defined, allowing the robot to respond to feedback from the Raspberry Pi and adjust its movements accordingly.
  
## Feedback Mechanism
The feedback mechanism consists of the communication between the Raspberry Pi and the Arduino Nano. To establish this communication, we utilized the Raspberry Pi's ```GPIO.HIGH``` functionality in conjunction with the Arduino's ```digitalRead()``` function.

- **Detection and Response**:
  - When a black wall is detected on one side of the horizontal line or when the red or green sign is not within the desired zones, the Raspberry Pi outputs a 3.3-volt signal to a designated pin connected to the Arduino.
  - The Arduino uses the ```digitalRead()``` function to detect this input and respond accordingly.

___
# Code and Pseudocode Overview
# Pseudocode for Arduino
```C++
// Initialize variables
int i = 0
bool buttonPressed = false  // Tracks if button is pressed
bool timeStarted = false    // Tracks if the 3-second timer started when i = 12
unsigned long startTime = 0 // Stores the time when i reaches 12
bool colorDetected = false  // Tracks if a color was detected
unsigned long colorStopTime = 0  // Stores the time when color detection paused

// Setup color sensor pins and other inputs/outputs
Setup pins for color sensor (S0, S1, S2, S3, sensorOut)
Setup pins for motor control (A0, A1, F, B)
Setup pins for digital inputs (left_wall_read, right_wall_read, left_pillar_read, right_pillar_read)
Attach servo to pin 10
Initialize Serial Monitor

// Setup loop
Loop {
    // If button not yet pressed, check if button is pressed
    If button is pressed:
        Set buttonPressed to true
        Debounce delay

    // If button was pressed once
    If buttonPressed is true:

        // Check if i reached 12 and the timer hasn't started
        If i == 12 and timeStarted is false:
            Record the start time
            Set timeStarted to true

        // If timer started and 3 seconds passed, stop the car
        If timeStarted is true and 3 seconds have passed since startTime:
            Stop the car
            Exit the loop (no further execution)

        // If a color was detected and 3 seconds haven't passed, skip color detection
        If colorDetected is true and 3 seconds haven't passed since colorStopTime:
            Check digital sensor inputs (walls, pillars)
            Return to the start of the loop

        // If a color was detected and 3 seconds have passed, reset color detection
        If colorDetected is true and 3 seconds have passed since colorStopTime:
            Reset colorDetected to false

        // If no color has been detected, proceed with color detection
        If colorDetected is false:
            Read Red, Green, and Blue pulse width values
            Map the pulse widths to final RGB values

            // If Red detected (based on thresholds)
            If Red is detected:
                Turn right
                Set colorDetected to true
                Record colorStopTime
                Increment i by 1

            // If Green detected (based on thresholds)
            Else If Green is detected:
                Turn left
                Set colorDetected to true
                Record colorStopTime
                Increment i by 1

            // If no color detected, check the digital sensor readings
            Else:
                Check digital sensor inputs (walls, pillars)

}

// Function to check digital sensor inputs for walls and pillars
CheckDigitalReads() {
    If left wall detected:
        Turn left
    Else If right wall detected:
        Turn right
    Else If left pillar detected:
        Turn left
    Else If right pillar detected:
        Turn right
    Else:
        Move forward
}

// Functions to get Red, Green, and Blue pulse widths
getRedPW()
getGreenPW()
getBluePW()

// Functions for movement
MoveForward() {
    Move the car forward
}

TurnLeft() {
    Turn the car left
}

TurnRight() {
    Turn the car right
}

StopCar() {
    Stop the car completely
}
```
[**CLICK HERE FOR ARDUINO CODE**](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Src/Arduino%20Code)

# Pseudocode for Raspberry Pi
```
Initialize Camera and GPIO:

Define camera properties:
Set camera device (0 for built-in, 1 for external).
Set resolution to width = 640, height = 400.
Set frame rate to 50 FPS.
Initialize the camera and wait for stabilization (e.g., sleep for 2 seconds).
Set Frame Parameters:

Define constants:
frame_height = 400
frame_width = 640
third_height = 123 (height for dividing frame into three parts)
bottom_line_y = 2 * third_height (Y-coordinate for the bottom line)
left_margin_end = 150 (end coordinate for the left margin)
right_margin_start = 490 (start coordinate for the right margin)
GPIO Pin Definitions:

Define GPIO pins for motor controls:
left_turn_black_wall = 17
right_turn_black_wall = 27
left_turn_pillar = 22
right_turn_pillar = 23
forward = 2
LED_PIN = 3 (for LED status indication)
Set GPIO mode to BCM and disable warnings.
Initialize all defined GPIO pins as output.
LED Blinking Mechanism:

Define variables for LED blinking:
blink_interval = 0.5
last_blink_time = current time
led_state = False
Function: blink_led_non_blocking()
Get the current time.
If the difference between current time and last_blink_time is greater than blink_interval:
Toggle led_state (turn LED on or off).
Update last_blink_time.
Define Movement Command Functions:

Function: left_command_black_wall()
Set left motor GPIO pin to HIGH.
Function: right_command_black_wall()
Set right motor GPIO pin to HIGH.
Function: left_command_green_pillar()
Set left turn GPIO pin to HIGH.
Function: right_command_red_pillar()
Set right turn GPIO pin to HIGH.
Function: forward_command()
Set forward GPIO pin to HIGH.
Set Minimum Contour Area for Detection:

Define min_contour_area = 1500 (adjustable based on testing).
Main Loop (Run Continuously):

While True:
Capture frame from the camera:
If frame capture fails, print error message and break.
Call blink_led_non_blocking().
Convert Frame to HSV:

Convert captured BGR frame to HSV color space for better color detection.
Define HSV Ranges for Color Detection:

Red Pillar:
lower_red1 = (0, 105, 15)
upper_red1 = (10, 255, 102)
lower_red2 = (145, 120, 70)
upper_red2 = (180, 255, 255)
Green Pillar:
lower_green = (55, 125, 17)
upper_green = (87, 255, 193)
Black Walls:
lower_black = (0, 0, 0)
upper_black = (180, 255, 8)
Create Masks for Color Detection:

Create mask for black walls using the defined HSV range.
Create masks for red and green using their respective ranges.
Contour Detection for Red Pillar:

Find contours for the red mask:
Initialize flags: red_detected = False, red_in_zone = False, red_area = 0.
If contours are found:
Identify the largest contour.
Calculate its area. If it exceeds min_contour_area:
Get bounding rectangle and calculate the center.
Draw bounding rectangle and center on the image.
Check if red contour is in the left zone:
Set red_detected or red_in_zone flags accordingly.
Contour Detection for Green Pillar:

Find contours for the green mask:
Initialize flags: green_detected = False, green_in_zone = False, green_area = 0.
If contours are found:
Identify the largest contour.
Calculate its area. If it exceeds min_contour_area:
Get bounding rectangle and calculate the center.
Draw bounding rectangle and center on the image.
Check if green contour is in the right zone:
Set green_detected or green_in_zone flags accordingly.
Determine Robot Actions Based on Color Detection:

If both red_detected and green_detected:
Compare red_area and green_area:
If red_area > green_area, execute right_command_red_pillar(), print message indicating right turn.
Else, execute left_command_green_pillar(), print message indicating left turn.
Else If only red_detected:
Execute right_command_red_pillar(), print message indicating right turn.
Else If only green_detected:
Execute left_command_green_pillar(), print message indicating left turn.
Else (no red or green detected):
Set all motor commands (left, right, and forward) to LOW.
Black Wall Detection Logic:

Check if black wall contacts the left or right part of the bottom line:
Define left_bottom_line as the mask region of the left side of the bottom line.
Define right_bottom_line as the mask region of the right side of the bottom line.
Check for black wall presence:
If black is detected on the left, call right_command_black_wall() and print message indicating right turn.
Else if black is detected on the right, call left_command_black_wall() and print message indicating left turn.
Else, print "No black detected: Move forward".
Exit Mechanism:

If 'q' is pressed, break the main loop.
Cleanup Resources:

Release the camera.
Destroy any OpenCV windows.
Clean up GPIO settings.
```
[**CLICK HERE FOR RASPBERRY PI CODE**](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Src/Raspberry%20Pi%20Code)
___
# Our Team
**Vaishant Ananth** is an 11th-grade student, he aspires to become a robotic engineer passionate about coding and hardware. He is actively involved in various technology challenges and dedicated to mastering both the software and hardware aspects of robotics.

**Ruba Darshan Ashok Kumar** is an 11th-grade student passionate about coding and web design. Experienced in competitive environments, demonstrating strong leadership skills. Aspiring robotic engineer dedicated to excellence in documentation and design. 

We both study at The Velammal International School, Ponneri
| Team Photo | Funny Photo|
|:-------------:|:--------------:|
|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/5011c82d5b573904ab9a71cb5e5145ce41017e83/Team%20Photo.jpg" alt="Image" width="431" height="350"/>|<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/5011c82d5b573904ab9a71cb5e5145ce41017e83/Funny%20Photo.jpg" alt="Image" width="431" height="350"/> |

We are very thankful to those who helped in completing our project.

Mrs.Anisree-Robotics Coach

Mrs.Hemalatha-Team Coordinator

Mr.Manoj-Lab assistant

___
# Our Journey
## Problems Encountered On The Way
We decided to use the TCS-34725 for the [color sensor](https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/main/Mechanism.md#color-sensor).

<div align="center">
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/d85731fa06d502daa4b1a9e671bb4cb95249c388/Photos/TCS-34725.jpg" width="200" height="200">
</div>
<br>
The sensor we initially used proved to be highly inaccurate when tracking fast-paced movement. As a solution, we opted to utilize the TCS-230, which effectively served as a superior alternative to the TCS-34725.
<br><br>
<div align="center">
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/c5296ea7fe148fb9da19b8f14dc1a5572e2f1d65/Photos/TCS-230.jpg" alt="TCS-230" width="200" height="200">
</div>

After assessing the situation, we decided to integrate a gyro sensor and an ultrasonic sensor. However, we found that the ultrasonic sensors provided very inaccurate readings during the robot's operation. To address this challenge, we considered using the EV3 system, but since neither of us had prior experience with it, we decided to set that option aside.

Ultimately, we opted to use the Raspberry Pi for wall avoidance and for managing the logic related to red and green pillars. Meanwhile, the Arduino Nano was chosen to handle thrust, steering, and lap counting, providing a more reliable solution for our needs.

### Problems Faced During Wall Avoidance
- **Complexity of Mathematical Distance Calculation**:
We initially opted for a mathematical approach to determine the distance of the walls relative to the robot. However, we quickly realized that this method was overly complex. We found that the problem could be tackled much more simply using the horizontal line logic described above.

- **Calibration of the Horizontal Line**:
Another challenge we encountered was the constant need to calibrate the ordinate of the horizontal line. After some adjustments and testing, we ultimately identified the optimal placement for the horizontal line, which improved our wall avoidance functionality.

### Problems Faced During Traffic Sign Identification
- **Detection of Small Red and Green Contours**:
The camera often detected small red and green contours due to reflections on the mat. To solve this, we set a minimum size threshold for the bounding rectangles, effectively filtering out noise and avoiding false detections.

- **Simultaneous Detection of Red and Green Signs**:
We encountered issues with both red and green traffic signs being detected at the same time. To address this, we implemented a comparison between the bounding rectangles of the two signs, ensuring that only the larger rectangle (indicating the closer sign) was detected and prioritized.

- **Confusion Between Traffic Signs and Black Walls**:
The robot became confused when it detected both black walls and traffic signs simultaneously. To resolve this, we programmed the robot to proceed with wall avoidance only when the traffic signs were in their designated zones, allowing for more accurate navigation.

### Problems Faced During Lap Count
Initially, we implemented the ```i++``` logic for the robot to count laps, which worked in theory. However, the robot would stop immediately upon detecting the last color, rather than completing the lap and stopping in the same section where it started. To resolve this, we incorporated a combination of boolean logic and the ```millis()``` function, ensuring the robot correctly finishes the lap before stopping in the designated section.

### Problems Faced During the Feedback Mechanism
Initially, we attempted to establish communication between the Raspberry Pi and Arduino using serial communication over a USB cable. However, this approach proved highly unreliable, as the Arduino often failed to read the commands sent by the Raspberry Pi. To overcome this issue, we switched to using the ```GPIO.high``` and ```digitalRead``` logic, as explained above, which significantly improved communication accuracy.
___
# Demonstration Videos
<table>
    <tr>
        <th>Open Challenge</th>
        <th>Obstacle Challenge</th>
    </tr>
    <tr>
        <td>
            <a href="https://www.youtube.com/watch?v=EHTh-pLtoqI" target="_blank">
                <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/b3e7fbf52a978b17ca052f3a2bb099cd07aaf9ab/Open%20Challenge%20Opening%20Page.png" alt="Open Challenge" width="800">
            </a>
        </td>
        <td>
            <a href="https://www.youtube.com/watch?v=NZUAv9LCASU" target="_blank">
                <img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/b3e7fbf52a978b17ca052f3a2bb099cd07aaf9ab/Obstacle%20Challenge%20Opening%20Page.png" alt=" Obstacle Challenge" width="800">
            </a>
        </td>
    </tr>
