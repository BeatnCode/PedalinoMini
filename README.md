<!-- <p align="center">
  <a href="https://github.com/fuegovic/PedalinoMini-Phoenix">
    <img src="./data/logo.webp" alt="PedalinoMini Phoenix Logo">
  </a>
</p> -->

# PedalinoMini Fork: SmartStomp

## ✨ Key Modifications

- **Fix for sequence step+/-**: original version did not work as expected
- **Sequence action: "Set Pedal Latch Status"**: sequence can be used to open preset with MIDI PC and recall status of effects
- **Pedal action: "Sequence Step Repeat"**: repeat current sequence step
- **Sequence action: "Set Last Bank"**: jump back to last bank
- **2nd action for analog input EXP1/2**: used to toggle wah wah on/off if input pin is pulled up
- **Display modifications/improvements**: 3 + 4 action names, adapt font size to bank name length
- **Bluetooth**: unstable with iPad/AUM (?)

---

## 💸 Bill of Materials

- **ESP32 board:** Any ESP32 board supported by [Arduino core for ESP32](https://github.com/espressif/arduino-esp32)
  - Tested on [DOIT ESP32 DevKit V1](https://github.com/SmartArduino/SZDOITWiKi/wiki/ESP8266---ESP32) 4M dual-mode Wi-Fi and Bluetooth module
- **OLED I2C display:** 0.96" or 1.3", 128x64, SSD1306/SH1106
- **USB MIDI hardware:**
  - Arduino ProMicro
- **DIN MIDI hardware:**
  - **MIDI OUT**: DIN5 connector, 2x 220 Ohm resistors
  - **MIDI IN**: DIN5 connector, 2x 220 Ohm resistors, 1N4001 diode, 6N137 optocoupler

## ⚡ Schematic

![Schematic](./docs/assets/Schematic_PedalinoMini.webp "Schematic")
[View Full Schematic](./docs/assets/Schematic_PedalinoMini.webp)

## 🔌 Pin Configuration Guide

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

See the documentation for a complete list of pin assignments and wiring details.

## Build

Coming Sooon

![Case](./docs/assets/case.png "Case")

## ⚖️ License

This project is licensed under the [GPL-3.0 License](LICENSE).