# kitbot-how-to
Guide for interacting with the KitBot

# Introduction
## Hardwares
MASLAB KitBot consists of two central components:  
1. A Raspberry Pi 5 computer - A powerful mini computer to run ROS 2 on Ubuntu 24.04

<p align="center">
<img src="image/pi5.png" width="50%" />
</p>

2. Raven - MASLAB custom circuit board to handle power and interaction with actuators and sensors

MASLAB KitBot also includes motors with encoders and servos to mobilize the robot. Teams can opt to use other motors and servos. More about actuators will be covered in another guide.

Raven also includes an onboard inertial measurement unit (IMU) and Qwiic (https://www.sparkfun.com/qwiic) connector system to connect the Pi 5 to other sensors. More about how to use sensors will be covered in another guide. 

To power these devices LiPo batteries will be provided.
> [!CAUTION]
> LiPo are **DANGEROUS**. Please review LiPo safety notes and attend LiPo lecture before using the kitbot with a battery.

# Hardware Setup
> [!NOTE]
> As a soldering practice ~~and cost cutting effort 💸~~, some kitbot part requires a bit of soldering. If you are new to soldering, need a refresh for soldering, or having any question/concern/problem, please reach out to a MASLAB staff during lab hours for assistance.

## Motor
TODO: Add images
The wheel motors come with uncrimped power and encoder wires. Below is the color code for the motor.

> <p align="center">
> <img src="image/motor_pins.png" width="50%" />
> </p>

The Red and White pins are for powering the motor. They can be screwed into the motor terminal blocks (to be explained later). The other pins are for encoders to count how many revolution has the motor rotated. To easily connect and disconnect these pins in the future, we can solder wires with headers onto them:

1. Pull out a black, yellow, green, and blue wires from the precrimped cable sets. 

2. Cut each of them in half to have precrimped leads for 2 motors.

3. Strip and solder the uncrimped ends to the motor's uncrimped encoder wires of the same colors.

Your end motor should look like this below. Make 2 of them for the driving wheels.

## Raspberry Pi
The Raspberry Pi 5 requires an active cooler to properly cool the board during heavy computations (i.e. image processing). To install the cooler, follow the installation guide at: https://datasheets.raspberrypi.com/cooling/raspberry-pi-active-cooler-product-brief.pdf 

## Raven Board
### Soldering
TODO: Add images
#### Motor terminals
Raven uses terminal blocks to connect to motors. Solder at least 2 of these terminals to connect to the kitbot wheel motors. Each terminal block is for one motor.

#### Encoder pins
Each motor may be equipped with an encoder. Populate Raven's encoder ports with black, blue, yellow, and green headers.

#### Servo pins
A typical servo has 3 pins for power and signal. Populate Raven's servo ports with black, red, and yellow headers.

#### Switch pins
Raven also have switch ports that are connected to the Pi's GPIOs for buttons / limit switches. Polulate them with any two color like your team's unique board identifier 😁

#### Pi connector
Raven is connected to the Raspberry Pi 5 through the standard Raspberry Pi 40 pins connector. To populate it:

1. Install the connector such that the exposed pins go from the bottom (side with MASLAB logo) to the top (side with components). Please be careful about this direction! Ask MASLAB staff if you are not sure.

2. Solder the connectors.

### Pi connection
Raven is designed as a compact Raspberry Pi HAT (Hardware Attached on Top) board. It meant to be installed directly on top of the Pi 5. To properly secure the board to the Pi, follow the [installation video](https://vilros.com/pages/pi-5-active-cooler-compatible-case-instruction-video) but do not populate the plastic covers. Instead, use Raven board as the top cover and leave the bottom cover uninstalled. We can mount the assembly onto the kitbot later through the bottom standoffs.

### Motor connection
Raven supports up to 5 motors with 5 optional encoders. If using encoder, make sure the the motor is modified according to [Motor](#motor). 

Each motor terminal block has 2 screw ports for power and ground for each motor. The left most block is motor 1 and right most block is motor 5.

Each encoder port is made of a row of black, blue, yellow, and green pins. The top most encoder port is for motor 1 and bottom most port is for motor 5.

To connect the motor power, loosen the screws of a terminal block, insert the power (red) wire into one screw ports and ground (white) into the other screw port, and tighten the screws.

> [!TIP]
> The order of the wire does not matter. Reversing them will reverse the rotation of the motor. Feel free to experiment and use whichever order makes the most sense for your software.

To connect the motor encoder, plug in the encoder wires, matching the colors into the encoder port of corresponding motor.

### Servo connection
Raven supports up to 4 servos. Each servo port is made of a column of black, red, and yellow pins. The left most servo port is for servo 1 and right most port is for servo 4.

To connect the servo, install the servo connector directly onto the servo pins, matching brown to black, red to red, and orange to yellow.

### Switch connection
Raven has 5 switches that gets connected to ground when closed. Each switch port is made of a row of your team's favorite colors.

## Battery
> [!WARNING]
> Information below are simply summary of LiPo safety notes for using the battery with the kitbot. For more details, please check LiPo safety notes.

### LiPo
The LiPo battery for the Pi is a LiPo battery with 3 cells connected in series (3S battery). The battery has an XT60 connector for power output and a JST-XH balancing lead for monitoring individual cells.  

<p align="center">
<img src="image/battery.jpg" width="50%" />
</p>

### Fused extension cable
For safety, a fused extension cable is required to be connected to the battery output when in use.  

<p align="center">
<img src="image/fused_cable.jpg" width="50%" />
</p>

### XT60 to XT30 adapter
The battery connector on the Raven board is a XT30 connector instead of the full size XT60. Therefore, an adapter is required to be connected to the fused extension cable.

<p align="center">
<img src="image/battery_adapter.png" width="50%" />
</p>

### Low voltage monitor
Low voltage monitor is also required to be connected to the battery balancing lead (JST-XH) during use.

> [!IMPORTANT]  
> Please have the low voltage monitor connected to the battery balancing lead **as long as the battery is in use**. When not in use, feel free to remove the monitor and store the battery in the battery safe bag.

<p align="center">
<img src="image/voltage_monitor.png" width="50%" />
</p>

> [!IMPORTANT]  
> The low voltage monitor is polarized. Please be careful when installing the balancing lead. The black wire should be connected to the first pin (BBX end) as shown in the previous picture. Below is a reference from older generation of the product.
> <p align="center">
> <img src="image/voltage_monitor_connection.png" width="50%" />
> </p>

### Full battery connection diagram

> <p align="center">
> <img src="image/battery_diagram.png" width="100%" />
> </p>




