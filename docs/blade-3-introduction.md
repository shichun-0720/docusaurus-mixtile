---
title: Blade 3 Introduction
type: docs
weight: 10
---

## Introduction

Mixtile Blade 3 is a low-cost, low-power SBC based on the next-generation, 8 nm Rockchip RK3588 CPU. It is ideal for quick development, AI-application prototyping, and edge computing, and it allows you to extend your deployment by clustering several Mixtile Blade 3 SBCs. It also features a 4-lane PCIe Gen3 port for communicating with other processing nodes, allowing for high-performance computing with minimal carbon footprint.

### Main Features

- CPU: Rockchip Octa-core Cortex-A76/A55 SoC processor RK3588

- NPU: Up to 6 TOPS

- Memory:
  Up to 32 GB LPDDR4/LPDDR5 memory, up to 256 GB eMMC storage

- HDMI interface:
  HDMI 2.1 output (8K @ 60 FPS or 4K @ 120 FPS),
  HDMI 2.0 input (4K @ 60 FPS)

- Video encoder: H.264/H.265 video encoder up to 8K @ 30 FPS

- Video decoder: H.265/H.264/VP9 video decoder up to 8K @ 60 FPS

- Camera Input: 4-lane MIPI-CSI

- PCIe expansion: Mini-PCIe socket with PCIe Gen 2.1, USB 2.0 support

- Storage expansion:
  4-lane PCIe Gen 3 in U.2 port,
  SATA 3.0 in U.2 port, Micro-SD 3.0 flash socket

- Ethernet expansion: Dual 2.5 gigabit Ethernet ports

- USB: Dual USB 3.2 Gen 1 Type-C ports, DisplayPort 1.4 A

- GPIOs: 30-pin GPIO socket
  (Digital I/O, I²C, USB 2.0, TTL UART, SPI, I²S)

- Software support: Preload customized Debian 11,
  Support other Linux distributions and Android 12 (**will release in future**)

- Power: USB1/PD Type-C Port support USB PD 2.0 protocol
  (Optional: 12 V DC standard SATA power in via U.2 port)

- Dimensions: 2.5-inch Pico-ITX form factor, 100 x 72 mm

### Connectors and Pinouts

**1. Block Diagram**

The Block diagram for the Blade 3 single-board computer is shown below with descriptions for each function of connectors and pinouts.

![Blade_3_block_diagram](Blade_3_block_diagram.png)

**2. Specs Layout**

The specification layout is depicted in the picture below, along with the ports accessible on Blade 3 for application-based development.

![blade3_quickStart](Blade3_quickStart.png)

**3. Connectors & Pinouts Description**

The following section lists the interfaces connector pin assignments, pin types with corresponding signal descriptions. The interface connectors on Blade 3 are listed in the table below.

**30PIN Header**

| Pin | Name             | Type   | Input/Output | Description                                         |
| --- | ---------------- | ------ | ------------ | --------------------------------------------------- |
| 1   | VCC\_5V0         | Power  | Output       | Power supply  for USB,5V output MAX 500mA.          |
| 2   | GND              | Power  | NA           | Power and signal reference ground.                  |
| 3   | USB20\_HOST0\_DM | LVDS   | BI           | USB20 HOST Port0 Data Minus                         |
| 4   | I2S2\_SDI\_M1    | signal | Input        | I2S2 data    input                                  |
| 5   | USB20\_HOST0\_DP | LVDS   | BI           | USB20 HOST Port0 Data Plus                          |
| 6   | I2S2\_SDO\_M1    | signal | Output       | I2S2 data  output                                   |
| 7   | GND              | Power  | NA           | Power and signal reference ground.                  |
| 8   | I2S2\_MCLK\_M1   | signal | Output       | I2S2 Master clock                                   |
| 9   | I2C5\_SDA\_M3    | signal | BI           | I2C5 Bus Date                                       |
| 10  | I2S2\_SCLK\_M1   | signal | BI           | I2S2 serial clock or BCLK                           |
| 11  | I2C5\_SCL\_M3    | signal | Output       | I2C5 Bus clock                                      |
| 12  | I2S2\_LRCK\_M1   | signal | BI           | I2S2 Left/Right channel clock                       |
| 13  | GND              | Power  | NA           | Power and signal reference ground.                  |
| 14  | GND              | Power  | NA           | Power and signal reference ground.                  |
| 15  | SPI4\_MISO\_M2   | signal | Input        | SPI4 Master input,Slave output                      |
| 16  | CAN2\_RX         | signal | Input        | CAN2 receive data                                   |
| 17  | SPI4\_MOSI\_M2   | signal | Output       | SPI4 Master output,Slave input                      |
| 18  | CAN2\_TX         | signal | Output       | CAN2 transmit data                                  |
| 19  | SPI4\_CLK\_M2    | signal | Output       | SPI4 clock                                          |
| 20  | GND              | Power  | NA           | Power and signal reference ground.                  |
| 21  | SPI4\_CS0\_M2    | signal | Output       | SPI4 Chip Select 0                                  |
| 22  | GPIO0\_B0        | signal | BI           | GPIO bank 0 port B0                                 |
| 23  | GPIO1\_A4        | signal | BI           | GPIO bank 1 port A4                                 |
| 24  | SARADC\_VIN7     | Analog | Input        | SAR ADC Channel 7 input                             |
| 25  | GND              | Power  | NA           | Power and signal reference ground.                  |
| 26  | SARADC\_VIN6     | Analog | Input        | SAR ADC Channel 6 input                             |
| 27  | PWM14            | signal | BI           | Pulse Width Modulation 14 input or output           |
| 28  | GND              | Power  | NA           | Power and signal reference ground.                  |
| 29  | PWM15            | signal | BI           | Pulse Width Modulation 15 input or output           |
| 30  | VCC\_3V3\_S0     | Power  | Output       | Power supply  for peripheral,3.3V output MAX 500mA. |

**2PIN FAN**        

| Pin | Name       | Type  | Input/Output | Description                                                    |
| --- | ---------- | ----- | ------------ | -------------------------------------------------------------- |
| 1   | VCC5V\_FAN | Power | Output       | Power supply  for FAN,5V output MAX 400mA.Control by GPIO3\_C0 |
| 2   | GND        | Power | NA           | Power reference ground.                                        |

**mini-PCIe**

| Pin | Name                        | Type   | Input/Output | Description                                                       |
| --- | --------------------------- | ------ | ------------ | ----------------------------------------------------------------- |
| 1   | MINIPCIE20\_WAKEN\_3V3\_L   | signal | Input        | Wake up signal from mini-PCIe device                              |
| 2   | VCC3V3\_MINIPCIE            | Power  | Output       | Power supply  for mini-PCIe device,3.3V output MAX 3A in all pins |
| 3   | NC                          | float  | NA           | No connected to this pin                                          |
| 4   | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 5   | NC                          | float  | NA           | No connected to this pin                                          |
| 6   | NC                          | float  | NA           | No connected to this pin                                          |
| 7   | MINIPCIE20\_CLKREQN\_3V3\_L | signal | Input        | PCIe2.0 Channel Reference clock request                           |
| 8   | NC                          | float  | NA           | No connected to this pin                                          |
| 9   | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 10  | NC                          | float  | NA           | No connected to this pin                                          |
| 11  | PCIE20\_2\_REFCLKN          | LVDS   | Output       | PCIe20 Port2 differential clock Negative                          |
| 12  | NC                          | float  | NA           | No connected to this pin                                          |
| 13  | PCIE20\_2\_REFCLKP          | LVDS   | Output       | PCIe20 Port2 differential clock Positive                          |
| 14  | NC                          | float  | NA           | No connected to this pin                                          |
| 15  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 16  | NC                          | float  | NA           | No connected to this pin                                          |
| 17  | NC                          | float  | NA           | No connected to this pin                                          |
| 18  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 19  | NC                          | float  | NA           | No connected to this pin                                          |
| 20  | W\_DISABLEN                 | signal | Output       | PCIE device wireless disable                                      |
| 21  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 22  | MINIPCIE20\_PERSTN          | signal | Output       | PCIE device reset                                                 |
| 23  | PCIE20\_2\_RXN              | LVDS   | Input        | PCIe20 receive differential Negative                              |
| 24  | VCC3V3\_MINIPCIE            | Power  | Output       | Power supply  for mini-PCIe device,3.3V output MAX 3A in all pins |
| 25  | PCIE20\_2\_RXP              | LVDS   | Input        | PCIe20 receive differential Positive                              |
| 26  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 27  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 28  | NC                          | float  | NA           | No connected to this pin                                          |
| 29  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 30  | NC                          | float  | NA           | No connected to this pin                                          |
| 31  | MINIPCIE20\_TX\_N           | LVDS   | Output       | PCIe20 transmit differential  Negative                            |
| 32  | NC                          | float  | NA           | No connected to this pin                                          |
| 33  | MINIPCIE20\_TX\_P           | LVDS   | Output       | PCIe20 transmit differential  Positive                            |
| 34  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 35  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 36  | MINIPCIE\_USB\_DM           | LVDS   | BI           | USB20 HOST Port1 Data Minus                                       |
| 37  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 38  | MINIPCIE\_USB\_DP           | LVDS   | BI           | USB20 HOST Port1 Data Plus                                        |
| 39  | VCC3V3\_MINIPCIE            | Power  | Output       | Power supply  for mini-PCIe device,3.3V output MAX 3A in all pins |
| 40  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 41  | VCC3V3\_MINIPCIE            | Power  | Output       | Power supply  for mini-PCIe device,3.3V output MAX 3A in all pins |
| 42  | NC                          | float  | NA           | No connected to this pin                                          |
| 43  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 44  | NC                          | float  | NA           | No connected to this pin                                          |
| 45  | NC                          | float  | NA           | No connected to this pin                                          |
| 46  | NC                          | float  | NA           | No connected to this pin                                          |
| 47  | NC                          | float  | NA           | No connected to this pin                                          |
| 48  | NC                          | float  | NA           | No connected to this pin                                          |
| 49  | NC                          | float  | NA           | No connected to this pin                                          |
| 50  | GND                         | Power  | NA           | Power and signal reference ground.                                |
| 51  | NC                          | float  | NA           | No connected to this pin                                          |
| 52  | VCC3V3\_MINIPCIE            | Power  | Output       | Power supply  for mini-PCIe device,3.3V output MAX 3A in all pins |

**30PIN MIPI-CSI**

| Pin | Name                     | Type   | Input/Output | Description                                          |
| --- | ------------------------ | ------ | ------------ | ---------------------------------------------------- |
| 1   | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 2   | MIPI\_CSI0\_RX\_D0N      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 0 Negative |
| 3   | MIPI\_CSI0\_RX\_D0P      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 0 Positive |
| 4   | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 5   | MIPI\_CSI0\_RX\_D1N      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 1 Negative |
| 6   | MIPI\_CSI0\_RX\_D1P      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 1 Positive |
| 7   | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 8   | MIPI\_CSI0\_RX\_CLK0N    | LVDS   | Input        | MIPI CSI0 receive  differential Clock 0 Negative     |
| 9   | MIPI\_CSI0\_RX\_CLK0P    | LVDS   | Input        | MIPI CSI0 receive  differential Clock 0 Positive     |
| 10  | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 11  | MIPI\_CSI0\_RX\_D2N      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 2 Negative |
| 12  | MIPI\_CSI0\_RX\_D2P      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 2 Positive |
| 13  | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 14  | MIPI\_CSI0\_RX\_D3N      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 3 Negative |
| 15  | MIPI\_CSI0\_RX\_D3P      | LVDS   | Input        | MIPI CSI0 receive  differential data lane 3 Positive |
| 16  | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 17  | MIPI\_CAM\_PWM2          | signal | Output       | PWM2 for LENS                                        |
| 18  | NC                       | float  | NA           | No connected to this pin                             |
| 19  | VCC\_3V3\_S0             | Power  | Output       | Power supply for sensor board,3.3V output            |
| 20  | MIPI\_CAM\_RESETN        | signal | Output       | GPIO out for sensor reset                            |
| 21  | NC                       | float  | NA           | No connected to this pin                             |
| 22  | MIPI\_CAM\_PDN           | signal | Output       | GPIO out for sensor power down                       |
| 23  | I2C3\_SDA\_M3\_MIPI      | signal | BI           | I2C5 Bus data                                        |
| 24  | I2C3\_SCL\_M3\_MIPI      | signal | Output       | I2C5 Bus clock                                       |
| 25  | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 26  | MIPI\_CAM2\_CLK\_M1\_3V3 | signal | Output       | Camera Master clock output                           |
| 27  | GND                      | Power  | NA           | Power and signal reference ground.                   |
| 28  | VCC\_5V0                 | Power  | Output       | Power supply for sensor board,5V output              |
| 29  | VCC\_5V0                 | Power  | Output       | Power supply for sensor board,5V output              |
| 30  | VCC\_5V0                 | Power  | Output       | Power supply for sensor board,5V output              |

**U.2 Plug**

| Pin | Name                     | Type   | Input/Output | Description                                  |
| --- | ------------------------ | ------ | ------------ | -------------------------------------------- |
| E1  | PCIE30\_REFCLKP\_SLOT    | LVDS   | Output       | RC PCIe30 differential clock Positive        |
| E2  | PCIE30\_REFCLKN\_SLOT    | LVDS   | Output       | RC PCIe30 differential clock Negative        |
| E3  | VCC\_3V3\_S0             | Power  | Output       | Power supply for IO                          |
| E4  | PCIE30X4\_CLKREQN\_M1\_L | signal | Output       | DM PCIe30 Channel Reference clock request    |
| E5  | PCIE30X4\_PERSTN\_M1\_L  | signal | Input        | DM PCIe30 Channel reset                      |
| E6  | PCIE30X4\_CLKREQN\_M3    | signal | Input        | RC PCIe30 Channel Reference clock request    |
| E7  | PCIE30\_PORT1\_REFCLKP   | LVDS   | Input        | DM PCIe30 differential clock Positive        |
| E8  | PCIE30\_PORT1\_REFCLKN   | LVDS   | Input        | DM PCIe30 differential clock Negative        |
| E9  | GND                      | Power  | NA           | Power and signal reference ground.           |
| E10 | PCIE30\_PORT1\_TX2P      | LVDS   | Output       | DM PCIe30 transmit differential  Positive    |
| E11 | PCIE30\_PORT1\_TX2N      | LVDS   | Output       | DM PCIe30 transmit differential  Negative    |
| E12 | GND                      | Power  | NA           | Power and signal reference ground.           |
| E13 | PCIE30\_PORT1\_RX2N      | LVDS   | Input        | DM PCIe30 receive differential  Negative     |
| E14 | PCIE30\_PORT1\_RX2P      | LVDS   | Input        | DM PCIe30 receive differential  Positive     |
| E15 | GND                      | Power  | NA           | Power and signal reference ground.           |
| E16 | NC                       | float  | NA           | No connected to this pin                     |
| E17 | PCIE30\_PORT0\_RX1P      | LVDS   | Input        | RC PCIe30 receive differential  Negative     |
| E18 | PCIE30\_PORT0\_RX1N      | LVDS   | Input        | RC PCIe30 receive differential  Positive     |
| E19 | GND                      | Power  | NA           | Power and signal reference ground.           |
| E20 | PCIE30\_PORT0\_TX1N      | LVDS   | Output       | RC PCIe30 transmit differential  Positive    |
| E21 | PCIE30\_PORT0\_TX1P      | LVDS   | Output       | RC PCIe30 transmit differential  Negative    |
| E22 | GND                      | Power  | NA           | Power and signal reference ground.           |
| E23 | I2C4\_SCL\_M0            | signal | Output       | I2C4 Bus clock                               |
| E24 | I2C4\_SDA\_M0            | signal | BI           | I2C4 Bus data                                |
| E25 | DUALPORT\_EN#            | signal | Output       | GPIO for Enable dual port,default low        |
| P1  | PCIE30X4\_WAKEN\_M1\_L   | signal | Output       | DM PCIE30 Wake up signal from RC             |
| P2  | PCIE30X4\_WAKEN\_M3      | signal | Input        | RC PCIE30 Wake up signal from DM             |
| P3  | PWRDIS                   | signal | Output       | GPIO for power disable to device             |
| P4  | IFDET                    | signal | Input        | GPIO for detect inteface of device           |
| P5  | GND                      | Power  | NA           | Power and signal reference ground.           |
| P6  | GND                      | Power  | NA           | Power and signal reference ground.           |
| P7  | NC                       | float  | NA           | No connected to this pin                     |
| P8  | NC                       | float  | NA           | No connected to this pin                     |
| P9  | NC                       | float  | NA           | No connected to this pin                     |
| P10 | PRSNT#                   | signal | Input        | GPIO for detect  device if present           |
| P11 | ACTIVITY#                | signal | Input        | GPIO for detect  device if activity          |
| P12 | GND                      | Power  | NA           | Power and signal reference ground.           |
| P13 | U2\_12V                  | Power  | Input        | Power supply for blade3,input 12V            |
| P14 | U2\_12V                  | Power  | Input        | Power supply for blade3,input 12V            |
| P15 | U2\_12V                  | Power  | Input        | Power supply for blade3,input 12V            |
| S1  | GND                      | Power  | NA           | Power and signal reference ground.           |
| S2  | SATA0\_TXP               | LVDS   | Output       | SATA30 Port0 transmit differential Positive  |
| S3  | SATA0\_TXN               | LVDS   | Output       | SATA30 Port0 transmit differential Negative  |
| S4  | GND                      | Power  | NA           | Power and signal reference ground.           |
| S5  | SATA0\_RXN               | LVDS   | Input        | SATA30 Port0 receive differential Positive   |
| S6  | SATA0\_RXP               | LVDS   | Input        | SATA30 Port0 receive differential Negative   |
| S7  | GND                      | Power  | NA           | Power and signal reference ground.           |
| S8  | GND                      | Power  | NA           | Power and signal reference ground.           |
| S9  | NC                       | float  | NA           | No connected to this pin                     |
| S10 | NC                       | float  | NA           | No connected to this pin                     |
| S11 | GND                      | Power  | NA           | Power and signal reference ground.           |
| S12 | NC                       | float  | NA           | No connected to this pin                     |
| S13 | NC                       | float  | NA           | No connected to this pin                     |
| S14 | GND                      | Power  | NA           | Power and signal reference ground.           |
| S15 | PCIE30X4\_PERSTN\_M3     | signal | Output       | RC PCIe30 Channel reset                      |
| S16 | GND                      | Power  | NA           | Power and signal reference ground.           |
| S17 | PCIE30\_PORT1\_TX3P      | LVDS   | Output       | DM PCIe30 transmit differential  Negative    |
| S18 | PCIE30\_PORT1\_TX3N      | LVDS   | Output       | DM PCIe30 transmit differential  Positive    |
| S19 | GND                      | Power  | NA           | Power and signal reference ground.           |
| S20 | PCIE30\_PORT1\_RX3N      | LVDS   | Input        | DM PCIe30 receive differential  Negative     |
| S21 | PCIE30\_PORT1\_RX3P      | LVDS   | Input        | DM PCIe30 receive differential  Positive     |
| S22 | GND                      | Power  | NA           | Power and signal reference ground.           |
| S23 | PCIE30\_PORT0\_RX0P      | LVDS   | Input        | RC PCIe30 receive differential  Negative     |
| S24 | PCIE30\_PORT0\_RX0N      | LVDS   | Input        | RC PCIe30 receive differential  Positive     |
| S25 | GND                      | Power  | NA           | Power and signal reference ground.           |
| S26 | PCIE30\_PORT0\_TX0N      | LVDS   | Output       | RC PCIe30 transmit differential  Negative    |
| S27 | PCIE30\_PORT0\_TX0P      | LVDS   | Output       | RC PCIe30 transmit differential  Positive    |
| S28 | GND                      | Power  | NA           | Po+A137:E196wer and signal reference ground. |

**3PIN DEBUG Header**

| Pin | Name                 | Type   | Input/Output | Description                   |
| --- | -------------------- | ------ | ------------ | ----------------------------- |
| 1   | UART2\_RX\_M0\_DEBUG | signal | Intput       | UART2 Receive Data for debug  |
| 2   | UART2\_TX\_M0\_DEBUG | signal | Output       | UART2 Transmit Data for debug |
| 3   | GND                  | signal | NA           | Signal reference ground.      |

### Dimensions of Blade 3

The detailed dimensions layout of Blade 3 device can be seen here:
[**Blade3_dimensions.pdf**](https://www.mixtile.com/app/uploads/2022/07/Blade3_dimensions.pdf)
