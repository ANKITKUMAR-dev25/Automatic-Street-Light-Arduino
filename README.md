# Automatic Street Light System using Arduino

This project is an energy-efficient **Automatic Street Light System** built using **Arduino Uno** and **LDR sensors**. The system automatically turns street lights on during darkness and off during daylight using ambient light detection.

---

## 🔧 Features

- Automatically controls street lights based on surrounding light intensity.
- Reduces energy consumption and improves efficiency.
- Simple and cost-effective circuit using basic components.

---

## 💡 How It Works

The system uses an **LDR (Light Dependent Resistor)** to detect ambient light levels. When the environment becomes dark (e.g., evening or night), the resistance of the LDR increases, and the Arduino triggers the **relay module** to switch ON the street light. When sufficient light is detected (e.g., daytime), the relay turns OFF the street light.

---

## 🧰 Technologies & Components Used

- **Arduino Uno**
- **LDR Sensor**
- **Relay Module (5V)**
- **Jumper Wires**
- **Breadboard**
- **Power Supply (USB or external)**

---

## ⚙️ Circuit Diagram

![Circuit Diagram](https://raw.githubusercontent.com/ANKITKUMAR-dev25/Automatic-Street-Light-Arduino/main/circuit-diagram.png)

> 📌 *Make sure the image file is uploaded to your GitHub repository under the correct path (or change the URL above if it's stored somewhere else).*

---

## 🛠️ Circuit Connections

| Component      | Arduino Pin     |
|----------------|------------------|
| LDR (via voltage divider) | A0 (Analog Input) |
| Relay IN Pin   | Digital Pin 8    |
| VCC & GND      | 5V and GND       |

- Connect the LDR in a voltage divider configuration with a resistor (~10kΩ).
- Connect the output of the divider to Arduino A0.
- Relay module’s IN pin connects to Digital Pin 8.

---


