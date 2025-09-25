# 🌃 Automatic Street Light System using Arduino

An energy-efficient **Automatic Street Light System** designed using **Arduino Uno** and **LDR sensors**. The system intelligently manages street lighting by detecting ambient light and automating ON/OFF switching, reducing manual work and energy consumption.

---

## 🔧 Features

* 🌗 **Auto Light Detection**: Lights automatically turn ON in darkness and OFF in daylight.
* 🔋 **Energy Efficient**: Reduces power consumption by operating only when needed.
* 💸 **Low Cost**: Built using basic and affordable electronic components.
* 🔄 **Fully Automatic**: No human intervention required.
* 🧩 **Modular Design**: Can be expanded to control multiple lights or integrated with IoT systems.

---

## 💡 How It Works

The system is based on the principle that an **LDR (Light Dependent Resistor)** changes its resistance based on the ambient light:

* **Daylight** ➝ Low Resistance ➝ Arduino reads high voltage ➝ **Relay OFF** ➝ Light OFF.
* **Darkness** ➝ High Resistance ➝ Arduino reads low voltage ➝ **Relay ON** ➝ Light ON.

The **Arduino** reads the analog signal from the LDR and controls a **relay module** to switch the street light accordingly.

---

## 🧰 Components Required

| Component                  | Quantity |
| -------------------------- | -------- |
| Arduino Uno                | 1        |
| LDR Sensor                 | 1        |
| 10kΩ Resistor              | 1        |
| Relay Module (5V)          | 1        |
| Jumper Wires               | Several  |
| Breadboard                 | 1        |
| Power Source (USB/Adapter) | 1        |
| LED/Bulb (for demo)        | 1        |

---

## ⚡ Circuit Diagram

> Include a circuit diagram here in your README. If not yet created, consider using tools like [Fritzing](https://fritzing.org/) or upload a hand-drawn image.

---

## 🛠️ Circuit Connections

| Component                 | Arduino Pin    |
| ------------------------- | -------------- |
| LDR (via voltage divider) | A0 (Analog In) |
| Relay IN Pin              | Digital Pin 8  |
| Relay VCC & GND           | 5V and GND     |
| Voltage Divider Resistor  | 10kΩ to GND    |

### 📌 Voltage Divider Setup

* One leg of LDR → 5V
* Other leg of LDR → A0
* 10kΩ resistor between A0 and GND

---

## 🧪 Arduino Code

```cpp
int ldrPin = A0;          // LDR connected to analog pin A0
int relayPin = 8;         // Relay connected to digital pin 8
int threshold = 500;      // Light threshold (tweak as needed)

void setup() {
  pinMode(relayPin, OUTPUT);
  digitalWrite(relayPin, HIGH); // Relay OFF initially
  Serial.begin(9600);
}

void loop() {
  int ldrValue = analogRead(ldrPin);
  Serial.println(ldrValue); // For testing light levels

  if (ldrValue < threshold) {
    digitalWrite(relayPin, LOW);  // Turn ON light (active-low relay)
  } else {
    digitalWrite(relayPin, HIGH); // Turn OFF light
  }

  delay(500);
}
```

### 🛠️ Adjusting Sensitivity

* You can fine-tune the `threshold` value by observing LDR readings (`Serial Monitor`) during day/night and setting a custom value accordingly.

---

## 🚀 Getting Started

1. Connect components as per the circuit diagram.
2. Upload the code using Arduino IDE.
3. Power the Arduino via USB or external adapter.
4. Observe the relay and connected light switching based on ambient lighting.

---

## 🔍 Troubleshooting

| Problem                    | Solution                                    |
| -------------------------- | ------------------------------------------- |
| Light not turning ON/OFF   | Check LDR wiring and threshold value        |
| Relay always ON or OFF     | Ensure correct relay wiring and logic level |
| Arduino not responding     | Check power and USB connection              |
| Serial Monitor not showing | Set baud rate to 9600 in Serial Monitor     |

---

## 💡 Possible Enhancements

* 📱 **Add IoT support** using ESP8266/NodeMCU to control remotely.
* 🌦️ Integrate **motion sensors (PIR)** to detect presence and improve efficiency.
* 🌓 Use **RTC (Real Time Clock)** module for scheduled lighting.
* 🔋 Add **solar power** integration for sustainable energy.
* 📊 Display status on an **LCD or OLED** screen.

---

## 📁 Repository Structure

```
Automatic-Street-Light-Arduino/
│
├── ArduinoCode/
│   └── street_light.ino
├── images/
│   └── demo.jpg
├── README.md
```

---

## 📜 License

This project is open-source and available under the MIT License. Feel free to modify and use for personal or educational purposes.

---

## 🤝 Contributing

Pull requests and contributions are welcome! Fork the repository, make your changes, and submit a PR.

---

## 🔗 Useful Links

* [Arduino Official Site](https://www.arduino.cc/)
* [LDR Working Principle](https://www.electronics-tutorials.ws/light/light_2.html)
* [Relay Module Guide](https://lastminuteengineers.com/relay-module-arduino-tutorial/)

---





