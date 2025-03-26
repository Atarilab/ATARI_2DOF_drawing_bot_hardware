# ATARI_2DOF_drawing_bot_hardware

GO HERE FOR SOFTWARE: [ATARI_2DOF_Drawing_Bot](https://github.com/Atarilab/ATARI_2DOF_Drawing_Bot)

This repository contains all the necessary information and files to build a ATARI 2DOF drawing robot.
The goal of this build is to have a system solely consisting of off the shelf parts and 3D printed parts while keeping costs down.

## Off the shelf parts

The parts listed here can be purchased from multiple online stores and retailers. If the linked stores provided in this documentation don't have the necessary parts in stock or don't deliver to your country, it shouldn't be a problem to order from a different retailer. In case you are not using the provided links for purchasing the parts, make sure that all specs and dimensions of the components match the ones listed here.

### Electronic parts

| Part | Description | Quantity | Link |
|-|-|-|-|
| Esp32 | Microcontroller running the SimpleFOC algorithm for motor control| 1 | [Link](https://www.conrad.de/de/p/az-delivery-esp32-dev-kit-c-unverloetet-kompatibel-mit-arduino-850037836.html) |
| SimpleFoc Mini v1.0 | Motor control board | 2 | Easiest to find on AliExpress via search for 'SimpleFOC Mini v1.0' |
| BLDC gimbal motor gbm2804h | Brushless DC motors | 2 | Easiest to find on AliExpress or Amazon via search for 'BLDC gimbal motor gbm2804h' |
| AS5600 Magnetic Encoder | Encoder for measuring motor angle | 2 | [Link](https://funduinoshop.com/elektronische-module/sensoren/bewegung-distanz/magnetinduktives-winkelmess-sensormodul-as5600) |
| Power supply, 12V, 3A | Power supply | 1 | [Link](https://www.conrad.de/de/p/mean-well-gst36e12-p1j-steckernetzteil-festspannung-12-v-dc-3000-ma-36-w-1439200.html) |
| DC power socket 5.5x2.1mm | Power supply socket | 1 | [Link](https://www.conrad.de/de/p/tru-components-niedervolt-steckverbinder-buchse-einbau-vertikal-5-5-mm-2-1-mm-1-st-1582319.html) |
| Micro USB cable | For ESP32 connection | 1 | - |

### Mechanical parts

| Part | Description | Quantity | Link |
|-|-|-|-|
| Ball bearing 17x26x5mm | - | 3 | - |
| Ball bearning 5x11x5mm | - | 2 | - |
| Screw M3x6mm flat head | - | 28 | - |
| Screw M3x10mm flat head | - | 8 | - |
| Screw M2x4mm round head | - | 12 | - |
| Screw M2x16mm flat head | - | 4 | - |

### Tools

| Tool | Comment | Link |
|-|-|-|
| Screwdrivers | According to which screws are being used | - |
| Dupont crimp tool | For crimping cables to custom lengths | [Link](https://www.berrybase.de/crimpzange-fuer-dupont-steckverbinder-an-kabel-awg-18-28) |
| Soldering iron | For soldering wires to DC power socket | - |
| 3D printer | For printing all structural parts | - |
| Pliers wrench | Not essential, but helpful for pressing in ball bearings | [Link](https://www.hoffmann-group.com/DE/de/hom/p/813702-180?tId=308&wayIntoCart=PLP&comingFromCategory=60-03-13-00-00&triggerSelectItemEvent=1) |
| Countersink hand tool | Not essential, but useful for cleaning up countersunk holes of 3D printed parts | [Link](https://www.hoffmann-group.com/DE/de/hom/p/150400-12%2C4?tId=509&wayIntoCart=SRP&triggerSelectItemEvent=1) |
| Utility knife | not essential, but practical for cleaning up sharp edges of 3D printed parts | [Link](https://www.hoffmann-group.com/DE/de/hom/p/844800-?tId=677&wayIntoCart=PLP&comingFromCategory=60-05-04-05-00&triggerSelectItemEvent=1) |

### Cables

Ideally the cables for this build are crimped to guarantee good contacts and durability. Alternatively, the cables can also be soldered if being done with caution.
Use this dupont crimp tool or a similar crimp tool with the corresponding dupont crimps so your cables will be compatbile with the rest of th electronics.
| Part | Link |
|-|-|
| Dupont crimp tool | [Link](https://www.berrybase.de/crimpzange-fuer-dupont-steckverbinder-an-kabel-awg-18-28) |
| Dupont crimps | [Link](https://www.berrybase.de/en/610-teiliges-dupont-crimp-steckverbinder-set-in-kunststoffbox) |


#### Power cable

#### Magnetic encoder cable

#### Motor cable

## 3D printed parts

| Part | Description | Quantity |
| - | - | - |
| Housing | Housing for all electronics components | 1 |
| Housing lid | Lid of the housing | 1 |
| Magnet pouch | Plate that holds the magnet for the AS5600 magnetic encoder | 2 |
| Shaft socket | Socket for connecting the shaft of the input gear to the motor | 2 |
| Input gear | Smaller gear of the transmission | 2 |
| Output gear | Bigger gear of the transmission | 2 |
| Rear Arm (L11 / L12) | - | 2 |
| Front arm L (L21) | - | 1 |
| Front arm R (L22) | - | 1 |
| Pen holder | Pen holder for a standard Stabilo pen; The model might neeed adjustment for other pens | 1 |

## Assembly

### Preparing components

- Clean up all rough edges and holes of the 3D printed components
- Solder 90-degree angled pin headers onto AS5600 PCB
- Solder straight pin headers onto ESP32 (Ideally only the pins that are necessary)
- Cut wires to the correct lengths and crimp dupont connectors onto their ends
- Solder wires onto the DC power socket (2x12V and 2xGND) and crimp dupont connectors onto the loose ends
- Cut motor cables to correct length and crimp dupont connectors onto the loose ends (3 pins)
- Screw M2x16 screw into the hollow shaft of the input gear

### Assembly of the housing
1. Mount the ESP32 board into the housing by using the mounting holes in the center of the housing. The Micro USB connector should be accessible from outside the housing.
2. Mount the two SimpleFOC Mini into the housing by using the outermost mounting holes
3. Connect the SimpleFOC data connectors (cables with 5 pins) to the SimpleFOC Minis and to the ESP32
4. Connect 3.3V supply cables to AS5600s
5. Connect I2C cables (2 pins) to the AS5600s and to the ESP32
6. Mount AS5600s into the housing by using the mounting holes next to the SimpleFOC Minis
7. Connect the 3.3V supply cables of the AS5600 magnetic encoders to the SimpleFOC Minis
8. Mount the DC power socket into the housing by using the large mounting hole in the wall next to the ESP32
9. Connect the cables of the DC power socket to the SimpleFOC Minis supply pins

### Assembly of the drive train
1. Mount motors onto the bottom side of the housing lid by using the inner mounting holes
2. Push the shaft of the input gear through the hollow motor shaft. Stick the shaft socket onto the end of the shaft of the input gear and insert a M2x16mm into the hole on the side of the shaft socket.
3. Insert the round magnet of the AS5600 magentic encoder into the magnet pouch
4. Align the holes of the magnet pouch and of the shaft socket with the mounting holes on the motor and screw four M3x10mm screws into the holes.
5. Press large ball bearings into the recesses on the bottom sides of the output gears
6. Press the output gears onto the round protrusions on the top side of the housing lid
7. Press small ball bearings into the holes on the ends of the rear arms
8. Press plastic pins at the ends of the front arms into the ball bearings on the rear arms
9. Press a big ball bearing into the hole on the end of the left front arm
10. Press the end of the right front arm into the big ball bearing of the left front arm
11. Mount the two links onto the output gears using M3x6mm screws
12. Connect the motor cables to the SimpleFOC Minis
13. Mount the assembled housing lid onto the housing using M3x6mm screws
