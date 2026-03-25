<!-- <p align="center">
  <a href="https://github.com/fuegovic/PedalinoMini-Phoenix">
    <img src="./data/logo.webp" alt="PedalinoMini Phoenix Logo">
  </a>
</p> -->

# "PedalinoMini" Fork: SmartStomp

![Render](docs/media/SmartStomp+_2025-Sep-16_06-58-21PM.png)

## Description

This is a "Pedalino Mini" build that I use to control an iPad Air 2 with "Overloud THU" as a guitar multi-effects processor, in combination with "OMEC Teleport" as an audio interface. The main idea behind this project is to map the hardware effect pedals visually to the software effect pedals using color.

One control sequence (11) is used to switch between 10 presets via "sequence step +/-".

10 THU presets are linked to 10 Pedalino banks (1 - 10), each configured with one sequence (1 - 10) which contains these actions:
- change THU preset with MIDI PC command
- set color of pedals
- set latch status of pedals (to keep hardware and software preset in sync)


## Software Modifications

- **fix for sequence step+/-**: original version did not work as expected
- **sequence action: "Set Pedal Latch Status"**: sequence can be used to open preset with MIDI PC and recall status of effects
- **pedal action: "Sequence Step Repeat"**: repeat current sequence step
- **sequence action: "Set Last Bank"**: jump back to last bank
- **2nd action for analog input EXP1/2**: used to toggle wah wah on/off if input pin is pulled up
- **display modifications/improvements**: 3 + 4 action names, adapt font size to bank name length
- **control display latch status indicator"**: ';' before action/bank name to disable latch status on display
- **recall last session**: Last preset & pedal color recalled at startup


## Bill of Materials

- **ESP32 board:** Any ESP32 board supported by [Arduino core for ESP32](https://github.com/espressif/arduino-esp32)
- **OLED I2C display:** 1.3", 128x64, SSD1306/SH1106
- **USB MIDI hardware:**
  - none
- **DIN MIDI hardware:**
  - **MIDI OUT**: DIN5 connector, 2x 10 Ohm, 1x 20 Ohm resistors (3.3 V configuration)
  - **MIDI IN**: DIN5 connector, 2x 220 Ohm resistors, 1N914 diode, 6N138 optocoupler
- **Other hardware:**
  - 9x DaierTek SPST Momentary Soft Touch
  - 4x 10 kOhm potentiometer
  - 4 * 4 + 3 = 19x WS2812B WS2812 4Pin RGB Led Chip
  - Mini560pro: 9 V -> 5 V


## Schematic

![Schematic](./docs/media/SmartStomp_schematic.jpg "Schematic")
[View Full Schematic](./docs/media/SmartStomp_info.pdf)


## Pin Configuration Guide

### Pedal Assignments
| Pedal  | GPIO  | Digital |  Analog | Type                     | 
|--------|-------|---------|---------|--------------------------| 
| 1      | 25    | ✅      | ❌      | Digital Switch            |
| 2      | 26    | ✅      | ❌      | Digital Switch            |
| 3      | 27    | ✅      | ❌      | Digital Switch            |
| 4      | 14    | ✅      | ❌      | Digital Switch            |
| 5      | 13    | ✅      | ❌      | Digital Switch            |
| 6      | 19    | ✅      | ❌      | Digital Switch            |
| 7      | 23    | ✅      | ❌      | Digital Switch            |
| 8      | 17    | ✅      | ❌      | Digital Switch            |
| 9      | 16    | ✅      | ❌      | Digital Switch            |
| 10     | 36    | ✅      | ✅      | Expression (ADC) internal |
| 11     | 39    | ✅      | ✅      | Expression (ADC) internal |
| 12     | 32    | ✅      | ✅      | Expression (ADC) internal |
| 13     | 33    | ✅      | ✅      | Expression (ADC) internal |
| 14     | 34    | ✅      | ✅      | Expression (ADC) EXP1     |
| 15     | 35    | ✅      | ✅      | Expression (ADC) EXP2     |


### System Pins

- **MIDI IN**: GPIO 15
- **MIDI OUT**: GPIO 4
- **USB MIDI**: GPIO 18, 2 (not connected)
- **LED Strip**: GPIO 5
- **OLED SDA**: GPIO 22
- **OLED SCL**: GPIO 21


## Pictures

![Design_1](./docs/assets/SmartStomp_CAD1.PNG "Design_1")
![Design_2](./docs/assets/SmartStomp_CAD2.PNG "Design_2")
![functions](docs/assets/SmartStomp_functions.png)
![Picture](./docs/media/DSCF9077.jpg "Picture")
![Picture](./docs/media/DSCF9072.jpg "Picture")
![Picture](./docs/media/DSCF9073.jpg "Picture")
![Picture](./docs/media/DSCF9086.jpg "Picture")

## Build

![](docs/media/IMG_4159.jpg)
![](docs/media/IMG_4158.jpg)
![](docs/media/IMG_4160.jpg)
![](docs/media/IMG_4161.jpg) 
![](docs/media/IMG_4168.jpg)
![](docs/media/IMG_4060.jpg) 
![](docs/media/IMG_4061.jpg) 
![](docs/media/IMG_4078.jpg) 
![](docs/media/IMG_4082.jpg) 
![](docs/media/IMG_4146.jpg) 
![](docs/media/IMG_4153.jpg) 
![](docs/media/IMG_4154.jpg) 
![](docs/media/IMG_4155.jpg) 
![](docs/media/IMG_4156.jpg) 
![](docs/media/IMG_4157.jpg) 


## ⚖️ License

This project is licensed under the [GPL-3.0 License](LICENSE).