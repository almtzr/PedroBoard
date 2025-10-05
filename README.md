# 📂 Pedro Board

## Two versions: 

- **Rev2** with 2 integrated modules: **NRF24L01** and **OLED 128x64**.
- **Rev3** with 4 integrated modules: Rev2 modules + **ESP8266-01** and **HC-05**

## Pedro Board Rev3: 

<div align="left">
    <img src="img/Spec_Board_Rev3.png" width="100%">
</div>

- **OLED Screen (128x64)**: Visualize data, debug in real-time, or create interactive menus.
- **NRF24L01**: Enable long-range wireless communication between Pedro or devices.
- **ESP8266-01 WiFi Module**: Bring your Pedro online with ease. (**Rev3 only**)
- **HC-05 Bluetooth Module**: Connect wirelessly to smartphones or other devices. (**Rev3 only**)
  
<div align="left">
    <img src="img/pedro_board_rev3.png" width="100%">
</div>

<br>

## ✅ Do It Yourself

Want to build Pedro from scratch? You can make your own Pedro Board by using the [Gerber file](src="PedroBoard_Rev3"). <br>
When you get your board, the microcontroller ATmega32u4 doesn’t have the correct bootloader yet, it's delivered with the factory bootloader. To make Pedro work with Arduino IDE, you first need to flash the Arduino Pro Micro bootloader into the Pedro board using the SPI pins as described below.

<div align="left">
    <img src="img/pedro_board_size.png" width="100%">
</div>

<br>

## 🛠️ What You Need:

- Your Pedro board (of course)
- PC with Arduino IDE installed
- An Arduino Pro Micro
- A Micro USB cable
- Some wires

<br>

## 📌 How to flash the bootloader?:

- Open Arduino IDE
- Connect the Arduino Pro Micro to the PC
- Select Arduino Pro Micro (ATmega32U4) as the target board
- Upload the "File" -> "Exemple" -> "Arduino as ISP" sketch to the Arduino Pro Micro
- When the upload is done disconnect the Arduino Pro Micro from the PC
- Connect the SPI pins of the Pedro board to the Arduino Pro Micro as shown:
    - Pedro Board => Arduino Pro Micro
    - GND         =>      GND (black)
    - VCC         =>      VCC (red)
    - SCK         =>      15 (orange)
    - MI          =>      14 (purple)
    - MO          =>      16 (green)
    - RST         =>      10 (yellow)
- Re-Connect the Arduino Pro Micro to the PC
- Select Arduino Pro Micro (ATmega32U4) as the target board
- Go to Tools > Burn Bootloader

🎯 Once done, disconnect the SPI wiring, plug the Pedro board to the PC and check in "Tools > Port" to ensure the board is recognized by Arduino IDE.

<div align="left">
    <img src="img/pedro_bootloader_wiring.png" width="100%">
</div>

<br>

## Mapping Pedro Board & Arduino

| Pedro Board  | Arduino Pin | Function    |
|--------------|-------------|-------------|
| Servo 1      | D5   | PWM Signal         |
| Servo 2      | D6   | PWM Signal         |
| Servo 3      | D9   | PWM Signal         |
| Servo 4      | D10  | PWM Signal         |
| Button 1     | A0   | Select Servo       |
| Button 2     | A1   | Rotation (forward)  |
| Button 3     | A2   | Rotation (backward) |
| LED Servo 1  | D13  | Servo LED         |
| LED Servo 2  | D11  | Servo LED         |
| LED Servo 3  | D8   | Servo LED         |
| LED Servo 4  | D7   | Servo LED         |
| NRF24L01 CE  | D4   | SPI Enable         |
| NRF24L01 CSN | D12  | SPI Chip Select    |
| OLED (SDA)   | D2   | I2C Data                  |
| OLED (SCL)   | D3   | I2C Clock                 |
| HC-05 (TX)   | D0   | UART RX        |
| HC-05 (RX)   | D1   | UART TX        |
| ESP8266 (TX) | D0   | UART RX             |
| ESP8266 (RX) | D1   | UART TX             |
| Switch 1     | N/A  | Select Mode Radio, Bluetooth, WiFi |
| Switch 2     | N/A  | Select Mode AT (HC-05)  |
| Pin A3       | A3   | Free                      |
| Pin A4       | A4   | Free                      |
| Pin A5       | A5   | Free                      |
| Pin RX       | RX   | Free                      |
| Pin TX       | TX   | Free                      |

---
