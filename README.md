# S32K_libuavcan
### libuavcan V1 bare-metal driver layer for the NXP S32K14x family of automotive-grade microcontrollers, featuring CAN-FD running at 4 Mb/s and 1 Mb/s in data and nominal phases, respectively.

An example project of it's usage for custom applications, and file dependencies used, is available in this **[Demo.](https://github.com/noxuz/libuavcan_demo)**
![alt text](https://s3-prod-europe.autonews.com/s3fs-public/NXP_logo%20web.jpg) 
| Peripheral used by this driver | Resources utilized |
| ------------- | ------------- |
| LPIT  | Channels 0,1 and 2, 3rd channel is available |
| FlexCAN | All message buffers from each instance; the frame's reception interrupt handler is enabled and its priority is set to default, could be modified to meet application-specific requirements  |


| Clocks in Normal RUN | Frequency set |
| ------------- | ------------- |
| CORE_CLK  | 80Mhz  |
| SYS_CLK | 80Mhz  |
| BUS_CLK  | 40Mhz  |
| FLASH_CLK  | 26.67Mhz  |

| Asynchronous clock sources | Divider value |
| ------------- | ------------- |
| SPLLDIV2  | 1  |

*Asynchronous dividers not mentioned are left unset and SCG registers are locked after initial setup.*
<br/>
<br/>
| Peripheral's functional clock  | Source and frequency |
| ------------- | ------------- |
| LPIT  | SPLLDIV2 @ 80Mhz  |
| FlexCAN  | SYS_CLK @ 80Mhz  |

| Pin setup | MUX |
| ------------- | ------------- |
| CAN0 RX | PTE4 |
| CAN0 TX | PTE5 |
| CAN1 RX | PTA12 |
| CAN1 TX | PTA13 |
| CAN2 RX | PTB12 |
| CAN2 TX | PTB13 |
| PTE10 | CAN0 transceiver's STB<br/> (UAVCAN node board only) |
| PTE11 | CAN1 transceiver's STB<br/> (UAVCAN node board only) |

*S32K146 and S32K148 although having multiple CANFD instances their evb's have
 only one transceiver, the other instances's  digital signals are set out to pin headers.*

 **For further details consult the S32K1xx reference manual [here.](https://www.nxp.com/webapp/Download?colCode=S32K1XXRM)**

 ### Copyright© 2020, NXP. All rights reserved.
 

