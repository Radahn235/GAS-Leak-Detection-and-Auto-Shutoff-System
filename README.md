# GAS-Leak-Detection-and-Auto-Shutoff-System

**🚨 Features**:
🧪 Real-time gas detection with MQ-6 sensor
🔊 Buzzer alarm on gas detection
🔄 DC motor shuts off gas using limit switch positioning
📲 Sends Telegram alert during leakage
🔘 Manual button to toggle gas ON/OFF\n
🛠️ Uses a custom bracket (not 3D printed) for motor and switches

**🔌 Pin Configuration (ESP32)**:
ESP32 Pin	Connected To
GPIO 25	Buzzer
GPIO 34	MQ-6 Sensor (A0)
GPIO 13	L298N ENA (PWM)
GPIO 14	L298N IN1
GPIO 27	L298N IN2
GPIO 4	Limit Switch (OFF)
GPIO 5	Limit Switch (ON)
GPIO 23	Push Button

**🧠 Working Logic**
🔥 When Gas is Detected
MQ-6 sensor detects gas level > 1200
Telegram message sent via bot
Buzzer sounds for 10 seconds
Motor turns regulator knob to OFF

**👆 Manual Button**
Taps the push button to toggle gas ON/OFF
Limit switches detect the knob's final position

**⚠️ Safety Precautions**
Warning: This system interacts with flammable gas.
Always test in a safe, open environment and use proper insulation. Keep manual controls and emergency shutoff methods ready.
