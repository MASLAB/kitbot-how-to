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
> LiPo are **DANGEROUS**. Please review LiPo safety notes and attend LiPo lecture before using the kitbot with a battery.

# Hardware Setup
## Battery
> [!WARNING]
> Information below are simply summary of LiPo safety notes. For more details, please check LiPo safety notes.

### LiPo
The LiPo battery for the Pi is a LiPo battery with 3 cells connected in series (3S battery). The battery has an XT60 connector for power output and a JST-XH balancing lead for monitoring individual cells.  

<p align="center">
<img src="image/battery.jpg" width="500px" />
</p>

### Fused extension cable
For safety, a fused extension cable is required to be connected to the battery output when in use.  

<p align="center">
<img src="image/fused_cable.jpg" width="500px" />
</p>

### Low voltage monitor
Low voltage monitor is also required to be connected to the battery balancing lead (JST-XH) during use. 

<p align="center">
<img src="image/voltage_monitor.png" width="50%" />
</p>

> [!IMPORTANT]  
> The low voltage monitor is polarized. Please be careful when installing the balancing lead. The black wire should be connected to the first pin (BX100 end) as shown in the picture.
> <p align="center">
> <img src="image/voltage_monitor_connection.png" width="50%" />
> </p>

## Raven Board
### Pi connection
Raven is designed as a compact Raspberry Pi HAT (Hardware Attached on Top) board. It meant to be installed directly on top of the Pi 5.




