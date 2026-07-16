# NorthernStudios iCE40-UltraPlus FPGA Dev Board

An open-source, compact development board designed around the **Lattice iCE40 UltraPlus (iCE40UP5K)** FPGA. Engineered for low-power applications, machine learning (TinyML), RISC-V softcores, and rapid hardware prototyping.

---

## Features

### 🛠️ Hardware Specification
*   **FPGA**: Lattice Semiconductor [iCE40UP5K-SG48](https://www.latticesemi.com/Products/FPGAandCPLD/iCE40UltraPlus)
    *   **Logic Cells**: 5,280 LUTs
    *   **Block RAM**: 120 Kbit
    *   **Single-Port RAM**: 1024 Kbit (128 KB SRAM, ideal for microcontroller memory)
    *   **DSP Blocks**: 8 (16x16 multiplier + 32-bit accumulator)
    *   **Hardened IP**: 2x I2C, 2x SPI
    *   **Constant Current Drivers**: 3x 24mA dedicated driver outputs (for RGB LED control)
*   **Storage**: 32Mbit (4MB) SPI Flash (W25Q32JV or similar) for FPGA bitstream and user data.
*   **Connectivity**: 
    *   USB Type-C interface for power, configuration, and UART.
    *   On-board USB-to-SPI/UART bridge (e.g., FT2232H or RP2040 debugger) for seamless programming and debug.
*   **Clocks**: 12 MHz MEMS/Crystal oscillator.
*   **Expansion**:
    *   Dual PMOD-compatible headers or standard 0.1" pitch GPIO breakout pins.
    *   Dedicated RGB LED connected to constant current outputs.
    *   User-assignable LEDs and tactile buttons.
*   **Power**: On-board regulators generating 3.3V (I/O & Flash) and 1.2V (FPGA Core) from USB 5V.

---

## Repository Structure

```
├── NS FPGA V2 iCE/         # KiCad Design Directory
│   ├── NS FPGA V2 iCE.kicad_pro   # KiCad Project File
│   ├── NS FPGA V2 iCE.kicad_sch   # Schematic Sheet
│   └── NS FPGA V2 iCE.kicad_pcb   # PCB Layout
├── .gitignore              # KiCad/Gitignore rules
└── README.md               # Project documentation
```

---

## Getting Started

### 🔌 Toolchain Setup
The iCE40 UltraPlus is fully supported by the open-source FPGA toolchain flow (**Project IceStorm**), allowing for fast, free, and unrestricted compilation.

1.  **Synthesis**: [Yosys](https://github.com/YosysHQ/yosys)
2.  **Place & Route**: [nextpnr](https://github.com/YosysHQ/nextpnr) (using the `--up5k` target)
3.  **Bitstream Packager**: [icepack](https://github.com/YosysHQ/icestorm)
4.  **Programming Tool**: [iceprog](https://github.com/YosysHQ/icestorm)

Alternatively, Lattice's proprietary software **Lattice Radiant** or **iCEcube2** can be used.

### 💻 Cloning the Project
```bash
git clone https://github.com/uzzambutt/NorthernStudios-iCE40-UltraPlus-FPGA-Dev-Board.git
```

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](file:///D:/NS%20FPGA%20V2/LICENSE) file for details.
