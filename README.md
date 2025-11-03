# 🎮 FPGA Ball Catcher Game – DE0 Board (VHDL)

A real-time **Ball Catcher arcade-style game** implemented on the **Altera DE0 FPGA** board using **VHDL**, **Quartus II 9.2**, and **ModelSim 6.5b**.  
This project demonstrates **VGA signal generation**, **PS/2 keyboard input decoding**, **finite-state machine (FSM) control**, and **real-time digital gameplay** — fully synthesized in hardware.

---

## 🧩 Project Overview

The player moves a paddle on the VGA screen to catch falling balls.  
The system generates VGA video output, handles PS/2 keyboard input, manages game logic (levels, scoring, and timer), and displays the remaining time on the **7-segment display**.

Game flow:
- The `control_unit` FSM manages levels and timing.  
- `ball.vhd` updates ball position, movement, and collisions.  
- `ps2_kbd.vhd` converts PS/2 scan codes into paddle movement.  
- `quad8regdisplay.vhd` drives the 7-segment display showing the countdown timer.  
- `ball_display2_1.vhd` (top entity) integrates all modules and connects I/O pins.

---

## ⚙️ Features

- 🎮 Paddle control via **PS/2 keyboard** or **on-board switch (SW2)**  
- 🖥️ **640 × 480 VGA output** at 60 Hz refresh  
- ⏱️ **Timer display** on 7-segment LEDs  
- 💯 **Scoring and multi-level progression**  
- 🔄 **FSM-based state control** (Start → Play → Next Level → Game Over)  
- 🧱 Modular design — easily simulated, debugged, and extended  

---

## 🧠 Module Descriptions

| File | Function |
|:---------------------|:--------------------------------------------------------------|
| `control_unit.vhd` | Finite State Machine controlling game flow, score thresholds, levels, and timing. |
| `ball.vhd` | Handles ball generation, motion, speed changes, and collision detection with paddle and screen edges. |
| `ps2_kbd.vhd` | Receives PS/2 scan codes and converts them into left/right paddle movements. |
| `quad8regdisplay.vhd` | Manages the DE0’s 7-segment display to show the countdown timer and remaining time. |
| `ball_display2_1.vhd` | **Top-level entity** integrating all modules, VGA sync, PS/2 interface, and score display connections. |

---

## 🧰 Tools & Hardware

- **FPGA Board:** Altera DE0  
- **Software:** Quartus II 9.2 Lite Edition  
- **Simulation:** ModelSim 6.5b  
- **Language:** VHDL (structural + behavioral)  
- **Peripherals:** VGA monitor, PS/2 keyboard, 7-segment display, on-board switches  

---

## 🧪 How to Run

1. **Download** the project ZIP file from this repository.  
2. **Extract** it to a local folder on your computer.  
3. **Open the project** in **Quartus II 9.2**.  
4. **Set `ball_display2_1`** as the **top-level entity**.  
5. **Compile** the design and program the DE0 FPGA board.  
6. **Connect** a VGA monitor and PS/2 keyboard to play the game.  
7. Optional: **Run simulations** in **ModelSim** for testing specific modules.

---
