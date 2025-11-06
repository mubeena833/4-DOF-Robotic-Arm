# 🤖 4-DOF Robotic Arm Using Arduino | Joystick and Bluetooth Control

This project demonstrates the design and implementation of a **4-Degree-of-Freedom (DOF) Robotic Arm** controlled via **joysticks** and **Bluetooth** using an **Arduino Uno**.  
It combines **manual control** and **wireless control** to perform real-time object manipulation with a servo-based robotic arm.

---

## 📘 Overview

- **Project Title:** 4-DOF Robotic Arm Control using Joystick and Bluetooth  
- **Associated with:** Rajiv Gandhi University of Knowledge Technologies, Srikakulam  
- **Microcontroller:** Arduino Uno  
- **Programming Language:** Arduino C/C++  
- **Communication Protocol:** UART (for Bluetooth module)  
- **Control Methods:**  
  - Manual control using dual-axis joysticks  
  - Wireless control using HC-05 Bluetooth module and smartphone app  

---

## 🧠 Project Aim

To design and develop a **servo-based robotic arm** capable of performing pick-and-place operations,  
controlled either by **joysticks** or remotely through **Bluetooth communication**.

---

## ⚙️ Components Used

| Component | Quantity | Description |
|------------|-----------|-------------|
| Arduino Uno | 1 | Main microcontroller |
| SG90 Servo Motors | 4 | For Base, Shoulder, Elbow, and Gripper movements |
| Joystick Module | 2 | For manual control |
| HC-05 Bluetooth Module | 1 | For wireless mobile control |
| Breadboard | 1 | For connections |
| External 5V Power Supply | 1 | To power servos |
| Jumper Wires | — | For circuit connections |

---

## 🔩 Circuit Diagram

![Circuit Diagram](Circuit%20Diagram.jpg)

**Connections Overview:**
- Servos: D3, D5, D6, D9  
- Joysticks: A0–A3  
- HC-05 Bluetooth: TX → D10, RX → D11  
- Common GND between Arduino, HC-05, and servo power supply  

---

## 💻 Working Principle

1. **Manual Mode:**  
   - Two joysticks provide analog input to the Arduino (0–1023).  
   - The values are mapped to servo angles (0–180°) using `map()` function.  
   - Arduino generates PWM signals to control the four servo motors.

2. **Bluetooth Mode:**  
   - Smartphone communicates with Arduino via HC-05 module using UART.  
   - Arduino interprets received commands and moves servos accordingly.  
   - Example: Sending `6` opens the gripper, `7` closes it, etc.

3. **Gripper Mechanism:**  
   - A servo-operated gripper acts as the **end effector**, converting servo rotation into opening/closing motion to pick and release objects.

---

## 🧾 Code Explanation

- Reads analog inputs from joysticks (A0–A3).  
- Maps them to servo positions with defined limits to avoid over-rotation.  
- Uses **PWM** to control each servo’s angle.  
- Handles Bluetooth commands via **SoftwareSerial** on pins D10 (RX) and D11 (TX).  
- Includes smooth motion for stable servo movement.  

---

## 📱 Mobile Control

You can use any **Bluetooth Terminal App** or **Arduino Bluetooth Controller** to send commands.  
Example command set:

| Command | Function |
|----------|-----------|
| `1` | Rotate base left |
| `2` | Center base |
| `3` | Rotate base right |
| `4` | Raise shoulder |
| `5` | Move elbow |
| `6` | Open gripper |
| `7` | Close gripper |
| `J` | Switch back to joystick mode |

---

## ⚙️ PWM & UART Communication

- **PWM (Pulse Width Modulation):** Controls servo angles by varying pulse width between 1 ms and 2 ms at 50 Hz.  
- **UART:** Enables serial data transfer between Arduino and Bluetooth module (HC-05) for wireless control.  

---

## 📈 Implementation Steps

1. Assemble robotic arm and mount servos (Base, Shoulder, Elbow, Gripper).  
2. Connect components as per circuit diagram.  
3. Upload Arduino code from `main.ino`.  
4. Pair phone with HC-05 (PIN: 1234 or 0000).  
5. Test joystick control, then Bluetooth control.  
6. Calibrate servo angles for smooth movement.

---

## 🚀 Features Added

- Dual Control: Joystick + Bluetooth  
- Real-time servo response  
- Smooth motion control with PWM  
- Compact and low-cost design  
- Easy to expand (can add sensors or STM32 controller later)

---

## 🎯 Output

- Robotic arm performs **pick and place** operations.  
- Operable through **joysticks** or **mobile Bluetooth app**.  
- Demonstrates principles of **embedded systems**, **robotics**, and **automation**.

---

## 📚 Learning Outcomes

- Understanding of **PWM-based servo control**  
- Implementation of **UART communication**  
- Integration of **Bluetooth control** with microcontrollers  
- Hands-on experience with **robotics and real-time control systems**

---

## 🧠 Future Enhancements

- Add sensors for feedback (closed-loop control).  
- Integrate camera and image recognition for object detection.  
- Implement inverse kinematics for coordinate-based control.  
- Upgrade controller to STM32 or ESP32 for faster response.

---

## 🧑‍💻 Author

**Name:** shaik mubeena
**Institution:** Rajiv Gandhi University of Knowledge Technologies, Srikakulam  


---

⭐ *If you like this project, don’t forget to star the repository!*
