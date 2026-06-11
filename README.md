# 🤟 Sign Language Recognition Glove

A wearable assistive technology project that translates hand gestures into text in real time using an ESP32, flex sensors, and an LCD display. The system is designed to bridge communication gaps by recognizing sign language gestures and displaying their corresponding output instantly.

---

## 📌 Overview

Communication can be challenging for individuals with hearing and speech impairments. This project explores a low-cost hardware solution that interprets hand gestures using sensor data and converts them into readable text.

The glove uses flex sensors to measure finger bending and an MPU6050 motion sensor to capture wrist orientation. An ESP32 processes the sensor readings and identifies predefined gestures using a rule-based classification algorithm. The recognized gesture is then displayed on a 16×2 LCD screen.

---

## 🚀 Features

- Real-time gesture recognition
- ESP32-based embedded system
- Flex sensor-based finger bend detection
- MPU6050 wrist orientation tracking
- LCD text output
- Gesture calibration system
- Lightweight and wearable design
- Expandable architecture for future machine learning integration

---

## 🛠️ Hardware Components

| Component | Quantity |
|------------|----------|
| ESP32 Development Board | 1 |
| Flex Sensors | 5 |
| MPU6050 Sensor Module | 1 |
| 16×2 I2C LCD Display | 1 |
| 10kΩ Resistors | 5 |
| Breadboard | 1 |
| Jumper Wires | Multiple |
| Fabric Glove | 1 |
| USB Cable | 1 |

---

## ⚙️ Working Principle

1. Flex sensors measure the bend of each finger.
2. MPU6050 captures wrist orientation (pitch and roll).
3. ESP32 reads and processes all sensor data.
4. A rule-based classifier compares sensor values against stored gesture thresholds.
5. The corresponding gesture label is displayed on the LCD.

### System Flow

```text
Flex Sensors + MPU6050
          ↓
      ESP32
          ↓
 Gesture Classification
          ↓
      LCD Output
```

---

## 🔬 Implemented Gestures

Current prototype supports recognition of:

- Letter A
- Letter B
- Letter C
- Letter D
- Letter E
- STOP
- ILY (I Love You)

Additional gestures can be added by defining new threshold ranges and calibration data.

---

## ⚠️ Challenges Faced

During development, flex sensors presented several challenges:

- Inconsistent readings across sensors
- Frequent recalibration requirements
- Sensor wear after repeated bending
- Limited long-term reliability

Several prototype iterations were required before achieving stable gesture recognition.

---

## 📚 Key Learnings

- Embedded Systems Development
- ESP32 Programming
- Sensor Integration
- Analog Signal Processing
- I2C Communication
- Hardware Prototyping
- Gesture Recognition Techniques
- Assistive Technology Design

---

## 🔮 Future Improvements

- Dual-hand gesture recognition
- Bluetooth/BLE connectivity
- Mobile application integration
- Voice output using Text-to-Speech
- Haptic feedback system
- Dynamic gesture recognition
- Machine Learning-based classification
- Expanded sign language vocabulary

---

## 🏗️ Tech Stack

- ESP32
- Arduino IDE
- C++
- MPU6050 Library
- LiquidCrystal_I2C Library

---

## 📂 Repository Structure

```text
Sign-Language-Recognition-Glove/
│
├── code/
│   ├── calibration_code.ino
│   └── gesture_glove.ino
│
├── images/
│   └── prototype.jpg
│
├── report/
│   └── Project_Report.pdf
│
└── README.md
```

---

## 👩‍💻 Author

**Sakshi Gupta**  
Automation & Robotics Engineering  
Vivekanand Education Society's Institute of Technology (VESIT)

---

### ✨ Turning Gestures into Words Through Embedded Intelligence
