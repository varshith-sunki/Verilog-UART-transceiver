UART Transceiver: RTL Analysis & Verification

📌 Project Overview
This project focuses on the analysis, simulation, and functional verification of an open-source Universal Asynchronous Receiver-Transmitter (UART) design written in Verilog. The goal of this study was to understand the RTL-to-Synthesis flow, with a specific focus on Finite State Machine (FSM) design, serial data framing, and waveform debugging.

🏗️ Architecture & Modules
The design consists of three primary hardware modules:

uart_tx.v (Transmitter): Converts parallel input data into a serial bitstream (adding Start, Data, and Stop bits) using a finite state machine and a baud-rate generator.

uart_rx.v (Receiver): Detects the start bit and samples the incoming serial data at the middle of the bit period to accurately reconstruct the parallel data.

impl_top.v (Top-Level): The wrapper module that instantiates and connects the TX and RX modules, routing the shared clock and reset signals.

🧪 Verification & Simulation
The design was verified using a self-checking testbench to ensure correct data transmission and reception.

Simulator: Icarus Verilog (Icarus Verilog 12.0)

Environment: EDA Playground

Testbench (tb.v): Instantiates the top module and feeds predefined byte sequences to the transmitter to verify that the receiver successfully echoes back the correct data.

Waveform Viewer: EPWave

Key Verification Checks:
Validated that the transmitter FSM transitions correctly: IDLE -> START -> DATA -> STOP -> IDLE.

Confirmed that the receiver accurately samples the data bits based on the baud rate timing.

Analyzed timing waveforms to ensure no data loss or framing errors occurred during transmission.

📂 Repository Structure
/rtl - Contains the hardware design files (uart_rx.v, uart_tx.v, impl_top.v)

/test - Contains the simulation testbenches (tb.v, tb_rx.v)

README.md - Project documentation

🚀 How to Run the Simulation
Navigate to EDA Playground.

Select SystemVerilog/Verilog for Testbench + Design.

Select Icarus Verilog as the simulator.

Paste all files from the /rtl folder into the Design pane on the right.

Paste tb.v from the /test folder into the Testbench pane on the left.

Check the Open EPWave after run box and click Run.
(Note: If EPWave throws a "Too much data" warning, adjust the time window to 0ns - 100000ns to view the key transmission waveforms).

"Simulation can be reproduced via the provided EDA Playground link (Icarus Verilog)."
https://www.edaplayground.com/

💡 Key Learnings
Gained practical experience in reading and tracing complex RTL code.

Learned how to use timing waveforms (EPWave) to debug serial communication issues.

Understood the importance of clock synchronization between asynchronous transmitter and receiver modules.

References:
https://github.com/ben-marshall/uart/tree/5fd2db850a41b65aa34f3a31c663fc8704c7abd8

👨‍💻 Author
VARSHITH SUNKI
Electronics Engineering Student | VLSI Enthusiast
