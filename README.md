# 🚪 Automatic Door Controller

Stepper-motor driven automatic door controller with keypad access, RF remote, obstacle detection and **earthquake detection** that opens the door automatically for safe evacuation. All operating parameters can be changed on site from the keypad and are kept in EEPROM.

![Arduino](https://img.shields.io/badge/Arduino_Mega-00878F?style=flat-square&logo=arduino&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Fritzing](https://img.shields.io/badge/Fritzing-CA2D2D?style=flat-square)

---

## ✨ Features

- **Keypad access** — 4×4 keypad with password entry and 16×2 I²C LCD feedback
- **RF remote control** — 4-channel receiver; the channel that opens the door is selectable
- **Stepper drive** — pulse/direction/enable control of a stepper driver, configurable opening travel (fractional turns supported)
- **End-stop homing** — closes until the limit switch triggers; homes automatically at power-up
- **Obstacle detection** — ultrasonic sensor blocks opening when something is in the door's path
- **Earthquake mode** — MPU6050 accelerometer continuously measures net acceleration; above the threshold the door opens and stays open until an authorised user ends the mode
- **On-site configuration via admin menus** — change user password, pair remote button, set hold-open time, set opening travel
- **Non-volatile settings** in EEPROM, survive power loss
- **Buzzer feedback** for key presses, success and error states
- **Relay output** for an external lock / auxiliary device

## 🔧 Hardware

| Component | Role |
|---|---|
| Arduino Mega 2560 | Main controller |
| Stepper motor + driver (PUL/DIR/EN) | Door movement |
| Limit switch | Closed-position end-stop |
| 4×4 matrix keypad | Password entry and configuration |
| 16×2 LCD with I²C backpack | User interface |
| 4-channel RF receiver | Remote control |
| HC-SR04 ultrasonic sensor | Obstacle detection |
| MPU6050 accelerometer | Earthquake detection |
| Relay module, buzzer | Lock output, audio feedback |

Full wiring diagram: `genel şema.fzz` (Fritzing).

## 📁 Repository layout

```
antalya_kapi_final_fixed.zip
└── antalya_kapi_final_fixed/
    ├── antalya_kapi_final_fixed.ino   # Firmware
    ├── genel şema.fzz                 # Wiring diagram (Fritzing)
    └── kapi_lib/                      # Libraries: Keypad, LiquidCrystal_I2C, MPU6050
```

## 🚀 Build & flash

1. Unzip the archive and copy the folders in `kapi_lib/` to your Arduino `libraries` directory.
2. Open `antalya_kapi_final_fixed.ino` in Arduino IDE.
3. Select **Arduino Mega 2560** and upload.

---

<sub>© Akif Baki Aydın — private project.</sub>
