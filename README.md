# kitbot-how-to
Guide for interacting with the KitBot

# Introduction
## Hardwares
MASLAB KitBot consists of two central components:  
1. Raven - MASLAB custom circuit board to handle power and interaction with actuators and sensors
2. A Raspberry Pi 5 computer - A powerful mini computer to run ROS 2 on Ubuntu 24.04
![pi5](image/pi5.png)

MASLAB KitBot also includes motors with encoders and servos to mobilize the robot. Teams can opt to use other motors and servos. More about actuators will be covered in another guide.

Raven includes an onboard inertial measurement unit (IMU) and Qwiic (https://www.sparkfun.com/qwiic) connector system to connect the Pi 5 to other sensors. More about how to use sensors will be covered in another guide. 

To power these devices LiPo batteries will be provided.
> [!CAUTION]
> LiPo are **DANGEROUS**. Please review LiPo safety notes and attend LiPo lecture before continuing with the Hardware connection.

# Hardware Setup
## Raven
### Pi connection
Raven is designed as a compact Raspberry Pi HAT (Hardware Attached on Top) board. It meant to be installed directly on top of the Pi 5.

### Battery connection
The battery for the Pi is a LiPo batter with XT60 connector. For safety, a fused extension cable is required to be connected to the battery output when in use. 
Low voltage monitor is also required to be connected to the battery balancing lead during use. 



