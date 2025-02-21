# LAB 3: TOF

The purpose of this lab was to get acquainted with the TOF sensors

# Prelab

From the TOF datasheet, the i2c address was 0x52. I plan to use both TOF sensors simultaneously, so I will need to change the i2c address of one of them. I wired the XSHUT pin to A3 for one of the TOF sensors. Upon startup, I will temporarily disable this TOF sensor, assign a new i2c address, and enable it. Using both sensors simultaneously is ideal because it lets you capture data from different directions without turning, enabling better obstacle avoidance and path planning. 

Currently, I plan to place one i2c sensor on the front and one i2c sensor on the right side of the robot. With sensors on the front and side, the robot will detect obstacles in front and on the side. This could avoid colliding with walls when making turns. This sensor configuration will miss obstacles behind the robot, so I will be careful when backing up. Overall, I think having sensors facing two different directions will give the most information to the robot. 

Here is a sketch of my wiring diagram. I used the two long connectors to the TOF sensors, ensuring I could place them anywhere on the robot. I used the short connector to connect the sensors to the Artemis. 

![image](https://github.com/user-attachments/assets/24f8e27f-46cc-4d0c-abe6-355124e38a58)

# Lab Tasks 

# TOF Sensor Connections

This shows the hardware connections for the TOF sensors to the QWIIC breakout board. It also shows the battery connected to the Artemis.

![PXL_20250218_204834579](https://github.com/user-attachments/assets/e4b174f3-69d6-40ad-9f4e-cc34e2169ea8)

# i2c connection

![image](https://github.com/user-attachments/assets/750244fc-d572-42f2-9d72-caebfe939504)

The TOF sensor was listed as 0x29 when I expected it to be 0x52. Upon further inspection, I realized that the i2c protocol uses the last digit (LSB) as the read/write bit. As a result, the original address (0x52) is bit shifted to the right, yielding 0x29. 

# TOF Sensor Mode

I initially read through the dataset to investigate the three different sensor modes. However, the Arduino library only supports two sensor modes (short, long), so I focused on those. The long mode is good up to 4 meters but is sensitive to lighting conditions. The short mode is only good up to 1.3 meters, but is robust to noise. Since 1.3 meters is about 4 feet, this mode will give enough distances for the vast majority of tasks I have to complete, so I chose to set both sensors on short mode to make them robust to noisy conditions. I tested the sensor's range, accuracy, and reliability at various distances. At each distance, I recorded 10 sensor measurements and sent them to the computer via Python. 




# 2 TOF Sensors + IMU

# TOF Sensor Speed

# Time vs Distance

# Time vs Angle

# 5000 Levels Tasks

# IR-based Sensors

# TOF Sensor Sensitivity to Color/Textures




