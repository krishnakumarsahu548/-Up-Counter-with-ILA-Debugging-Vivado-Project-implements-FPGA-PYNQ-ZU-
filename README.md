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

# Circuit
<img width="1823" height="648" alt="image" src="https://github.com/user-attachments/assets/c1aeac86-fcf1-464d-8c4e-4fd5b4438a9c" />

# 🚀 How to Run

Clone repo

Open Vivado → Create Project

Add HDL files & XDC

Add ILA from IP Catalog

Synthesize → Implement → Generate Bitstream

Program device

Open Hardware Manager → Debug

# FPGA Resource Utilization (Vivado Report)
Below utilization numbers are generated after synthesis & implementation for the PYNQ-ZU (XCZU5EG-1SFVC784) device.
<img width="552" height="288" alt="image" src="https://github.com/user-attachments/assets/ef81184f-f0b6-4d5b-845f-dd7c12b9de17" />
<img width="551" height="323" alt="image" src="https://github.com/user-attachments/assets/f494aeba-3d84-4ad0-bdaa-e194464528c6" />
# ⏱ Timing Summary
<img width="1032" height="252" alt="image" src="https://github.com/user-attachments/assets/9935409f-39bd-416f-823a-00ff616d4761" />
# 🔋 Power Estimation
<img width="1087" height="490" alt="image" src="https://github.com/user-attachments/assets/5bec655b-2d1e-4cc3-843d-8539399bd36e" />




