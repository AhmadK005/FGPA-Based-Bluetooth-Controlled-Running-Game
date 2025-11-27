# FPGA-Based Bluetooth-Controlled Running Game

A side-scrolling running game implemented in **Verilog** on an FPGA board and controlled over **Bluetooth** from a phone.  
Obstacles spawn at randomized intervals and the player must jump to avoid them.

---

## 🎮 Overview

- Player character runs continuously across the screen.
- Obstacles are generated with pseudo-random timing.
- A **Bluetooth controller** (phone app / external device) sends jump commands to the FPGA.
- Game logic, collision detection, and score tracking are all implemented in hardware.

This project was built as the final project for an FPGA / digital systems course.

---

## 🧱 Main Features

- **Fully hardware-implemented game loop**
- **Bluetooth input** decoded on the FPGA
- **Randomized obstacle spawning**
- **Collision detection** and game over state
- **Score counter** that increases the longer you survive

---

## 🛠 Hardware & Tools

- Intel / Altera FPGA development board  
- Intel Quartus Prime project (`FinalProject.qpf`)
- Verilog HDL (`*.v` files)
- External Bluetooth module (e.g., HC-05/HC-06) connected to FPGA UART pins

> Update this section with your exact board/model if you want it perfectly accurate.

---

## 🧩 System Architecture

At a high level, the design is split into:

- **Clock / PLL modules** – generate the game and UART clocks  
- **Bluetooth RX module** – receives and decodes jump commands  
- **Game state module** – handles player position, jump physics, and game over  
- **Obstacle generator** – spawns obstacles using a pseudo-random timer  
- **Collision detector** – checks overlap between player and obstacles  
- **Display / output logic** – drives LEDs / 7-segment / VGA (depending on your setup)

You can add a block diagram image here later, for example:

```text
[Bluetooth Controller] --> [UART RX] --> [Game Logic] --> [Display / LEDs]
                                          ^
                                          |
                                       [Clock / PLL]
