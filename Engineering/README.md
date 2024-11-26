# Electrical Architecture of the Robo-EV Project



The development of the electronic and electrical architecture has the advantages of improving the overall vehicle electrical performance, maximizing the optimization of product cost, reducing the repeated development of vehicle model platforms, and shortening the vehicle development cycle; it has the characteristics of improving the performance, reliability, and safety of the vehicle's electrical system and reducing the failure rate of the overall vehicle electrical system. The Robo-EV electronic and electrical architecture is a stable and reliable electronic and electrical architecture solution obtained through the analysis of various aspects such as function, performance, cost, and assembly under specific constraints such as market demand input, functional requirements, regulations, and design requirements.


## 1. Power Distribution

### 1.1 Low-Voltage Power Supply

According to the functional configuration and demand analysis of the Robo-EV project, the low-voltage power supply platform architecture of the Robo-EV vehicle is divided into three levels:

The first level is a 12V lead-acid battery, which provides static power consumption for all electronic control units and components. Based on the calculation of the static current of the electrical components of the Robo-EV vehicle, this lead-acid battery needs to be configured with a specification of 12V and 60Ah, and the vehicle can be left stationary for more than 14 days.

The second level has power supplies for the intelligent driving system with a 50A fuse, the steering system with a 60A fuse, the braking system with a 60A fuse, the parking system with a 60A fuse, the body system with a 60A fuse, the DCDC electronic control system with a 60A fuse, etc. The power supply of each system is rationally configured through a high-current fuse.

The third level power supplies are respectively for the headlamp with a 10A fuse, the position lamp with a 10A fuse, the vehicle control unit with a 10A fuse, the motor controller with a 5A fuse, the power battery management system with a 5A fuse, the instrument with a 5A fuse, and other electrical equipment with a 20A fuse.

The low-voltage power distribution architecture diagram is as follows:

![](https://alidocs.dingtalk.com/core/api/resources/img/5eecdaf48460cde568dd34f46d29411b62faf2e15de7b704ae485ceceedc35ee8c6e1e7f6b7eda22ec177c308ebd5304a2cc16ca443f5fab47202adf34fce08c149f09193e96d5c1bb1a4ae2338e59d3a6f68d69855997784fb4c8ed7016461c?tmpCode=89cf2e5a-ae15-46ac-bcf6-28de4a761264)

<center>Figure 1 Low-Voltage Power Distribution Architecture</center>

Power supply for motor controller (MCU), power supply for power battery management system (BMS), vehicle control unit (VCU)

### 1.2 High-Voltage Power Supply

According to the project functional configuration and functional analysis, the high-voltage power supply electrical platform architecture of the Robo-EV vehicle is divided into three levels, and the specific functions of each level are as follows:

The first level is the power battery. According to market and configuration analysis, a lithium iron phosphate power battery with a capacity of 14.98KWh, a rated voltage of 144V, and a single cell capacity of 104Ah is required to be matched. This battery meets the national AC charging standard for AC; the power battery system has functions such as fault diagnosis, charging information interaction, and overheat protection.

The second level is the multi-in-one controller, which has 4-way outputs, positive and negative input of the power battery, MSD, and high-voltage interlock functions.

The third level is 250A for the motor controller, 50A for the air conditioning compressor and air conditioning electric heating equipment, and 60A for the high-voltage auxiliary equipment.

The high-voltage power distribution architecture diagram is as follows:

![](https://alidocs.dingtalk.com/core/api/resources/img/5eecdaf48460cde568dd34f46d29411b62faf2e15de7b704ae485ceceedc35ee8c6e1e7f6b7eda22ec177c308ebd530428aaefaf8475675564901a63e241ea9221f2853dd5a00725325dfd7099772b2e28b377bde9a9469a4fb4c8ed7016461c?tmpCode=89cf2e5a-ae15-46ac-bcf6-28de4a761264)

Figure 2 High-Voltage Power Distribution Architecture

## 2. Bus Network Architecture

The bus network architecture is divided into body CANB, chassis CANC, and intelligent driving CANA. The VCU serves as the communication gateway for the three bus network segments of CANA, CANB, and CANC. There are 3 network nodes including VCU, instrument, and voice robot connected on the body CANB. Among them, 120Ω network termination resistors are configured on the VCU and instrument electronic control units; there are 9 nodes including power battery management system, VCU, motor controller, on-board charger, DCDC controller, braking controller, steering controller, parking controller, and remote control receiver connected on the chassis CANC. Among them, 120Ω termination resistors need to be configured on the VCU and motor controller electronic control units; there are 2 bus nodes including VCU and intelligent driving controller connected on the CANA. Among them, 120Ω termination resistors need to be configured on the VCU and intelligent driving controller electronic control units. The communication rate of intelligent driving CANA, body CANB, and chassis CANC is 500kbit/s. The bus network architecture diagram is as follows:

![](https://alidocs.dingtalk.com/core/api/resources/img/5eecdaf48460cde568dd34f46d29411b62faf2e15de7b704ae485ceceedc35ee8c6e1e7f6b7eda22ec177c308ebd53042ec16c39fcc838f5134269f8552783f6d429ee1bcd6949f634f1df75219562c27e4099129b76c3804fb4c8ed7016461c?tmpCode=89cf2e5a-ae15-46ac-bcf6-28de4a761264)

<center>Figure 3 Vehicle Network Architecture</center>

