# Embedded IoT Homework 2
## Dual PWM, OLED Monitoring & GitHub Submission

**Student Name:** Hira Shahzad  
**Project:** Embedded-IoT-Homework-2  
**Platform:** ESP32 DevKit V1  
**Framework:** Arduino with PlatformIO  
**Simulation:** Wokwi  

---

## 1. Project Overview

This project demonstrates dual Pulse Width Modulation (PWM) using an ESP32 microcontroller. Two LEDs fade smoothly with different PWM frequencies. An SSD1306 OLED display is added to monitor the live duty-cycle percentages and configured PWM frequencies of both LEDs.

The project is implemented and tested using Wokwi simulation and the physical ESP32 hardware kit.

## 2. Objectives

- Control two LEDs using separate ESP32 GPIO pins.
- Generate PWM signals at different configured frequencies.
- Implement smooth LED fading by changing the PWM duty cycle.
- Interface an SSD1306 OLED display using I2C communication.
- Display the live duty-cycle percentage and configured PWM frequency for each LED.
- Upload the project files and evidence to the course GitHub repository.

## 3. Components Required

- ESP32 DevKit V1
- One red LED
- One green LED
- Two 220 Ω current-limiting resistors
- SSD1306 128×64 I2C OLED display
- Breadboard and jumper wires
- USB data cable
- VS Code with PlatformIO
- Wokwi simulator

## 4. Task 1 — Dual LED PWM

In Task 1, two LEDs are connected to separate ESP32 GPIO pins. The PWM duty cycles are varied to create a smooth fading effect.

### PWM Configuration

| Parameter | Red LED | Green LED |
|---|---|---|
| GPIO Pin | GPIO 25 | GPIO 26 |
| PWM Frequency | 1000 Hz | 5000 Hz |
| PWM Resolution | 10 bits | 10 bits |
| Duty Cycle Range | 0–1023 | 0–1023 |

The 10-bit PWM resolution provides 1024 possible duty-cycle values, from 0 to 1023. The duty cycle is converted into a percentage for monitoring.

**Duty Cycle Percentage Formula:**

`Duty Cycle (%) = (Current Duty / Maximum Duty) × 100`

## 5. Task 2 — OLED Monitoring

In Task 2, an SSD1306 OLED display is added to the dual-LED PWM circuit. The display shows the duty-cycle percentage and configured PWM frequency of both LEDs.

### OLED Configuration

| OLED Pin | ESP32 Connection |
|---|---|
| VCC | 3V3 |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

**I2C Address:** `0x3C`

### OLED Display Information

- Red LED: live duty-cycle percentage
- Red LED: configured frequency of 1000 Hz
- Green LED: live duty-cycle percentage
- Green LED: configured frequency of 5000 Hz

The OLED refreshes periodically while the LEDs continue fading. The duty-cycle percentages change as the LEDs fade, while the configured frequencies remain constant.

## 6. LED Wiring

### Red LED
- ESP32 GPIO 25 connects to a 220 Ω resistor.
- The resistor connects to the red LED anode (+).
- The red LED cathode (−) connects to GND.

### Green LED
- ESP32 GPIO 26 connects to a 220 Ω resistor.
- The resistor connects to the green LED anode (+).
- The green LED cathode (−) connects to GND.

Each LED uses its own current-limiting resistor.

## 7. Software and Libraries

The project is developed using C++ with the Arduino framework in PlatformIO.

Libraries used:

- `Adafruit SSD1306`
- `Adafruit GFX Library`
- `Wire` for I2C communication

### Project Files

## 7. Project Structure

```text
Embedded-IoT-Homework-2/
├── platformio.ini
├── diagram.json
├── wokwi.toml
├── README.md
├── src/
│   └── main.cpp
└── screenshots/
    ├── task1-hardware1.jpeg
    ├── task1-hardware2.jpeg
    ├── task2-oled-hardware.jpeg
    ├── task1-circuit.jpg
    ├── task1-working.jpg
    ├── task2-oled-output.jpg
    └── task2-circuit-oled.jpg
```

### Hardware and Simulation Evidence

| Filename | Description |
|---|---|
| `task1-hardware1.jpeg` | First physical hardware photo for Task 1 |
| `task1-hardware2.jpeg` | Second physical hardware photo for Task 1 |
| `task2-oled-hardware.jpeg` | Physical hardware photo showing the OLED and LEDs |
| `task1-wokwi.png` | Wokwi simulation screenshot for Task 1 |
| `task2-wokwi.png` | Wokwi simulation screenshot for Task 2 |
| `task2-oled-display.png` | OLED display simulation screenshot |
| `task2-pwm-monitoring.png` | PWM duty-cycle and frequency monitoring screenshot |

Save all images inside the `screenshots` folder using the filenames listed above. Make sure the filenames match your actual image files.


## 8. Testing and Verification

The following checks are performed for the project:

1. Verify that both LEDs are connected to their assigned GPIO pins.
2. Verify that each LED has a separate current-limiting resistor.
3. Confirm that both LEDs fade smoothly.
4. Verify the configured PWM frequencies in the program.
5. Confirm that the OLED initializes and displays both LEDs' information.
6. Check that the duty-cycle percentages update during fading.
7. Build and test the project in PlatformIO and Wokwi.
8. Test the circuit on the physical ESP32 hardware kit.
9. Capture screenshots and photographs as evidence.

**Note:** Mark each test as completed only after verifying it on the actual simulator or physical hardware.

## 9. Repository and Submission

**GitHub Repository:**  
https://github.com/HiraShahzad-795/IOT-Projects-1035.git

**Project Folder:** `Embedded-IoT-Homework-2`

The project folder contains the source code, PlatformIO configuration, Wokwi circuit configuration, README, and testing evidence.

### Required Commit Messages

- Task 1 commit: `task1 completed`
- Final submission commit: `complete homework`

## 10. Conclusion

This project demonstrates how an ESP32 can control two LEDs using PWM signals with different configured frequencies. The SSD1306 OLED provides real-time monitoring of the duty-cycle percentages and configured frequencies. The project combines GPIO control, PWM, I2C communication, embedded C++, simulation, and physical hardware testing.
