# -Up-Counter-with-ILA-Debugging-Vivado-Project-implements-FPGA-PYNQ-ZU-
This project implements a 3-bit Up Counter on the PYNQ-ZU (Zynq UltraScale+) board

This project implements a 3-bit Up Counter on the PYNQ-ZU (Zynq UltraScale+) board using:

Differential 125 MHz Clock

Active-Low Reset Button (BTN0)

On-board PL User LEDs (LED0, LED1, LED2)

Integrated Logic Analyzer (ILA) for real-time signal debugging

Verilog RTL + Vivado 2023.x flow

This repository contains HDL code, XDC constraints, and ILA configuration required to run and debug the design on the PYNQ-ZU board.

# 🧩 Project Overview

This design uses a 125 MHz differential clock input (clk_p, clk_n) from the board.
The internal up-counter increments every time the clock divider overflows.
The current 3-bit count value drives the three PL LEDs.

An onboard ILA core is connected to:

count[2:0]

clk_div[26:0]

reset

Ye ILA Vivado Hardware Manager me real-time waveform capture ke liye use hota hai.
# Tool use

| Component           | Version                            |
| ------------------- | ---------------------------------- |
| Vivado Design Suite | 2023.x / 2024.x                    |
| Board               | PYNQ-ZU (Zynq Ultrascale+ XCZU5EG) |
| Language            | Verilog HDL                        |
| Debug Tool          | ILA (Integrated Logic Analyzer)    |

# 🎛 Hardware Used

PYNQ-ZU Board

PL LEDs (LED0–LED3)

Push Buttons (BTN0–BTN3)

Differential Clock 125 MHz

HP I/O Bank (1.2V user IO standard)

PYNQ-ZU Features (Manual Page 28 & 13) include:

4 PL LEDs

4 PL buttons

125 MHz differential clock source

PMODs

RGB LEDs

SYZYGY ports

![WhatsApp Image 2025-11-17 at 14 31 02_8c5bf90e](https://github.com/user-attachments/assets/b21c35d5-bf44-49bd-b094-bafcf3d2e788)


# 🔍 ILA Debugging Features

ILA captures:

count[2:0] – real-time counter value

clk_div[26:0] – clock divider waveform

rest – button press detection

Debug steps:

Program FPGA

Open Vivado Hardware Manager

Set triggers (e.g., when count == 3)

Arm ILA

See waveform changes live
<img width="1920" height="1013" alt="image" src="https://github.com/user-attachments/assets/fe13cec4-f5b2-49aa-84d6-2f6023d95afc" />

