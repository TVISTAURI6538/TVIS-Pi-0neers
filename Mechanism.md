# Mechanism 
## Ackerman Steering
We have implemented **Ackerman's steering mechanism** for the steering system. We chose this system because it met all our requirements and was the best fit for our robot. We conducted extensive research to find the ideal steering system for our robot. We tested several steering systems, including rack and pinion steering, electronic rear motor steering, 4-wheel steering, and hydraulic steering. However, each of these mechanisms had significant drawbacks that would hinder our robot's performance. The servo-based Ackerman's steering emerged as the perfect choice, offering excellent speed and precise turning, even on sharp turns.

<div align="center">
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/0bd9c5a31b9391ca47272338321cdebba609e37c/Ackerman%20Steering.jpg" alt="Ackerman Steering Image">
</div>
<br>

We selected the Ackermann steering system for several reasons. First, it helps reduce tire wear by minimizing tire scrubbing during turns, ultimately extending the lifespan of the tires. Additionally, this system provides improved handling and stability, effectively preventing understeer and oversteer by ensuring that all wheels follow their intended paths during turns. Moreover, vehicles equipped with Ackermann steering exhibit a more predictable and consistent steering response, which is particularly crucial for high-performance vehicles that require precise control. Furthermore, this steering system contributes to safer cornering, especially at higher speeds, by reducing the likelihood of tire scrubbing and maintaining better traction during turns. Lastly, Ackermann steering enhances maneuverability in low-speed maneuvers such as parking and tight turns, allowing for a smaller turning radius and making the vehicle more maneuverable and easier to handle in confined spaces. Considering these factors, it was evident that Ackermann's mechanism was the best choice for our needs.

## Color Sensor
The color sensor mechanism works by emitting light onto a surface and detecting the reflected light across different wavelengths, corresponding to red, green, and blue colors. The TCS-230 sensor then converts the intensity of these colors into frequency signals, with each color having its own frequency range. These signals represent the intensity levels of the detected colors, which are processed by a microcontroller, such as an Arduino Nano or Raspberry Pi. Calibration of the sensor involves adjusting sensitivity levels and thresholds to accurately differentiate between specific colors, like blue and orange while minimizing interference from ambient lighting.

<div align="center">
<img src="https://github.com/TVISTAURI6538/TVIS_Pi-0neers_Future-Engineers-2024/blob/0f27da842771c92ef4721414f0df5f12735e8014/Color%20Sensor%20Mechanism.jpg" alt="Color Sensor Mechanism">
</div>
<br>

Once the color data is processed, the robot makes real-time decisions based on the detected pattern, such as turning left or right in response to the colors on the game mat. This allows the robot to navigate smoothly and efficiently. The system’s precision ensures accurate color recognition and responsiveness, even during fast-paced movements, enhancing the robot’s ability to react quickly to changes in its environment.

## Servo Motor
A servo mechanism is a control system that enables precise control over the angular or linear position, velocity, and acceleration of an object. It typically consists of three main components: a motor, a feedback device, and a controller. The motor, which is usually a DC motor or a stepper motor, generates the necessary torque to move the output shaft to a specified position. The feedback device, such as a potentiometer or encoder, measures the current position of the output shaft by converting its rotational position into an electrical signal that can be interpreted by the controller.

The controller plays a crucial role by receiving the desired position input, often from a microcontroller, and comparing it to the feedback from the feedback device. If a discrepancy exists between the desired and actual positions, the controller adjusts the motor's operation to reduce this error, thereby moving the shaft to the correct position. This combination of components allows servo mechanisms to achieve high precision and repeatability, making them widely used in robotics, automation, and applications requiring accurate positioning, such as camera gimbals, robotic arms, and remote-controlled vehicles.
