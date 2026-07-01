# STM32 Industrial Encoder Node

A compact industrial encoder node developed for robotics and automation systems, providing reliable magnetic position sensing and robust multi-drop communication in electrically noisy industrial environments. The hardware is designed around the STM32G431 microcontroller and AS5047D magnetic encoder, with an emphasis on reliability, protection, manufacturability, and field serviceability.

The design targets distributed motion control applications where multiple encoder nodes communicate with a central controller over an RS485 network while operating close to BLDC motors and switching power electronics.

---

## Project Overview

This project implements a complete industrial encoder interface board capable of:

- Reading absolute angular position from a magnetic encoder
- Communicating over an RS485 multi-drop network
- Supporting hardware configurable node addressing
- Operating from a 12 V  power supply
- Generating regulated 5 V and 3.3 V rails onboard
- Providing USB-C firmware programming and debugging support
- Operating reliably in high EMI industrial environments

---

## Hardware Specifications

| Item | Specification |
|------|---------------|
| MCU | STM32G431CBT6 |
| Encoder | AS5047D Magnetic Encoder |
| Communication | RS485 |
| Power Input | 12 V DC |
| Output Rails | 5 V, 3.3 V |
| PCB Size | 50 mm × 50 mm |
| PCB Layers | 4-Layer FR4 |
| Design Software | KiCad 9.0.8 |

---

# Repository Structure

```
Industrial-Encoder-Node/
│
├── README.md
│
├── hardware/
│   ├── Industrial_Encoder_Node.kicad_pro
│   ├── Industrial_Encoder_Node.kicad_sch
│   ├── Industrial_Encoder_Node.kicad_pcb
│   ├── Industrial_Encoder_Node.pdf
│   ├── stackup_description.txt
│   │
│   ├── gerbers/
│   │
│   └── bom/
│
├── docs/
│   ├── Design_Document.pdf
│   ├── Firmware_Architecture.pdf
│   ├── Protocol_Specification.pdf
│   ├── Bring_Up_Procedure.pdf
│   ├── Risk_Analysis.pdf
│   ├── Assumptions_Open_Questions.pdf
│   │
│   └── diagrams/
│
└── images/
    ├── PCB_3D.png
    ├── PCB_Top.png
    ├── Block_Diagram.png
    └── System_Architecture.png
```

---

# Deliverables

## Hardware

| Deliverable | Description |
|-------------|-------------|
| Schematic | Complete circuit design |
| PCB Layout | 4-layer PCB layout |
| Gerber Files | Manufacturing files |
| Drill Files | PCB drilling information |
| Bill of Materials | Component list |
| Stack-up | PCB layer information |

---

## Documentation

| Document | Description |
|----------|-------------|
| Design Document | Complete hardware design explanation |
| Firmware Architecture | Embedded software architecture |
| Communication Protocol | Packet format and communication design |
| Bring-Up Procedure | Initial hardware validation process |
| Risk Analysis | Failure modes and mitigation |
| Assumptions & Open Questions | Design assumptions and trade-offs |

---

# System Architecture

The board receives a 12 V DC industrial supply through the input connector, followed by reverse polarity protection and transient suppression circuitry. A synchronous buck converter generates the regulated 5 V rail, which powers the communication interface while also feeding a low-noise LDO regulator to generate the 3.3 V rail for the STM32 microcontroller and magnetic encoder.

The STM32 communicates with the AS5047D magnetic encoder using SPI to obtain high-resolution angular position data. Encoder information, diagnostics, and configuration data are exchanged with a host controller through the RS485 communication interface. A hardware DIP switch allows field configuration of the node address without requiring firmware modification. USB-C and SWD interfaces provide firmware programming and debugging support.

---

# Key Design Features

- Industrial 12 V power input
- Reverse polarity protection
- Surge and ESD protection
- On-board 5 V and 3.3 V power generation
- High-resolution magnetic encoder interface
- Multi-drop RS485 communication
- Hardware configurable node addressing
- USB-C firmware programming
- SWD debugging interface
- Four-layer PCB optimized for signal integrity and EMI reduction

---

# PCB Overview

- 50 mm × 50 mm board size
- Four-layer FR4 construction
- Dedicated ground plane
- Dedicated power distribution layer
- Functional component placement by subsystem
- Optimized routing for power, communication, and high-speed signals
- Designed for standard low-cost PCB fabrication

---

# Design Objectives

The hardware was developed with the following objectives:

- Reliable industrial operation
- Compact mechanical footprint
- Ease of manufacturing
- Robust communication
- Simplified field maintenance
- Improved noise immunity
- Expandability for future firmware features

---

# Software Architecture

The accompanying firmware architecture defines dedicated software modules responsible for encoder management, communication, diagnostics, configuration, and overall system health monitoring. A timer-driven architecture ensures deterministic encoder sampling while maintaining reliable communication and diagnostics.

---

# Manufacturing Outputs

The repository includes:

- Complete KiCad project
- Manufacturing Gerbers
- Drill files
- Bill of Materials
- PDF schematic
- Hardware documentation
- Firmware architecture
- Validation procedures

Everything required for PCB fabrication, assembly, and further firmware development is included.

---

# Author

**Anusha**

B.Tech Electronics and Communication Engineering

Industrial Encoder Node Hardware Design Project

Designed using **KiCad 9**
