## 🔥 ESP32-Based Gas Leak Detection & Auto Shutoff System

This project is a **safety system** using **ESP32**, a **gas sensor (MQ-6)**, **L298N motor driver**, and **limit switches** to detect LPG leaks and automatically shut off the gas valve. It also sends real-time **alerts to Telegram** and activates a buzzer for warning.

### 📦 Features

* 🚨 Detects LPG gas leaks using the MQ-6 analog gas sensor.
* 🔔 Activates a buzzer when a gas leak is detected.
* 🔧 Automatically rotates a gas regulator knob to the OFF position using a DC motor and L298N driver.
* 🛑 Uses limit switches to detect end positions of the gas knob (ON/OFF).
* 📱 Sends Telegram alerts when gas is detected.
* 🔘 Includes a manual push button to toggle the gas valve ON/OFF.
* 💻 Displays gas level and status on Serial Monitor for debugging.

### 🛠️ Hardware Components

* ESP32 development board
* MQ-6 gas sensor
* L298N motor driver
* 12V DC motor (connected to regulator)
* 2 limit switches (for ON and OFF end detection)
* Push button (for manual toggle)
* Buzzer (for alert)
* External power supply (for motor)
* WiFi connection

### 🔌 Pin Connections

* Buzzer → GPIO 25
* MQ-6 Analog Output → GPIO 34
* L298N ENA (PWM control) → GPIO 13
* L298N IN1 → GPIO 14
* L298N IN2 → GPIO 27
* Limit Switch (OFF) → GPIO 4
* Limit Switch (ON) → GPIO 5
* Push Button → GPIO 23

### 🌐 Network & Telegram Setup

* Connects to your WiFi using provided SSID and password.
* Sends Telegram alert using your bot token and chat ID.
* Message sent: “⚠ GAS LEAK DETECTED! Buzzer Activated & Gas Valve Closing!”

### ⚙️ Functional Logic

* Continuously reads analog value from MQ-6 sensor.
* If gas level > 1200:

  * Sends alert via Telegram (only once).
  * Activates buzzer for 10 seconds.
  * Rotates motor to OFF position using limit switch.
* Manual button toggles gas knob ON or OFF using motor and switches.
* Uses PWM (8-bit, 5 kHz) to control motor speed via L298N ENA pin.
* Includes debounce logic for the push button to prevent false triggers.

### 📝 Notes

* Make sure the motor bracket and limit switches are properly aligned with the gas regulator.
* Ensure power to the motor is sufficient (use external power if needed).
* Use proper precautions when dealing with real LPG gas and test in a controlled environment.
