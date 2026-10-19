# SRD - System Requirements Document
**Project**: Olympus — Open-Source Modular Hardware and Software Platform
**System Scope**: Olympus platform standard, reference hardware implementations, and software development ecosystem.

## 1. Introduction and Scope
### 1.1 Purpose
This document defines the system-level requirements of the Olympus platform, an open-source hardware and software ecosystem designed to enable the development, integration, and use of modular embedded systems.

Olympus establishes a common set of hardware, electrical, mechanical, and software interface requirements that allow compatible boards to be designed and integrated into the platform. These requirements are intended to support both the development of custom expansion boards and the use of the reference hardware provided by the project.

The Olympus reference hardware comprises four boards: the Zeus Processor Board, the Ares Power Board, the Hephaestus Motion Board and the Argus computational vision board. These boards provide example implementations of the platform architecture and allow users to build and experiment with a complete Olympus system without designing their own hardware.

In addition to the hardware specifications, Olympus aims to provide an open software development ecosystem, including device drivers, firmware, development tools and support for Linux, RTEMS, and Zephyr.

The project will publish the hardware designs, schematics, source code, interface specifications and technical documentation required to reproduce, modify, and extend the platform, subject to the applicable licenses.

### 1.2 System Overview
The Olympus platform is based on a modular architecture in which specialized electronic boards are interconnected through two system buses. The electrical pinout and connector assignments are defined in the Interface Control Document, while the corresponding functional, electrical, mechanical and compatibility requirements are specified in this document.

Any board intended to be compatible with Olympus shall comply with the applicable platform requirements and interface specifications. Compliance with these requirements is intended to ensure that independently developed boards can be integrated into a compatible Olympus system.

The reference configuration consists of the Zeus Processor Board, the Ares Power Board, the Hephaestus Motion Board, and the the Argus computational vision board. The minimum configuration consists of the Ares Power Board and the Zeus Processor Board, providing power supply and processing capabilities, respectively.

The Olympus platform is not limited to these four reference boards. Its specifications are intended to enable third-party developers and researchers to design additional compatible boards and extend the platform's functionality.

### 1.3 Reference Hardware
The Olympus project provides four reference board designs:

- **Zeus Processor Board**: provides the primary processing and system management capabilities.
- **Ares Power Board**: provides the platform's power supply infrastructure.
- **Hephaestus Motion Board**: provides motion-related functionality.
- **Argus computational vision board**: provides a camera interface and computational vision with AI capabilities.

The detailed capabilities of each board, together with their interfaces and operational requirements, are specified in the corresponding sections of this document and in the associated technical documentation.

### 1.4 Software and Development Tools
The Olympus software ecosystem is intended to provide the software components and development tools required to use, program and extend the platform.

The project aims to provide device drivers and software support for Linux, RTEMS and Zephyr together with the necessary firmware and development documentation

The scope of software support, including the supported boards, peripherals, operating system versions and development tools, shall be defined in the corresponding software requirements and compatibility documentation.

## 2. General System Requirements
### 2.1 Open Hardware and Software
- **OLY-SYS-001 — Open Hardware Compliance:** All hardware designs developed as part of the Olympus project, including the reference boards and bus interconnect, shall be publicly available under open hardware licenses that permit use, study, modification, and redistribution.

- **OLY-SYS-002 — Open Software:** All software developed specifically for the Olympus platform, including firmware, device drivers, and development tools, shall be distributed under open-source licenses that permit use, study, modification, and redistribution.

### 2.2 Modular Architecture
- **OLY-SYS-003 — Modular Architecture:** The Olympus platform shall support a modular architecture in which processing, power management, and motion control functions are implemented in separate boards.

- **OLY-SYS-004 — Maintenance and Debug Interface:** Each reference board shall provide a maintenance and debugging interface suitable for its programmable components and intended functionality.

- **OLY-SYS-005 — Reprogrammability:** Each reference board containing programmable components shall provide a mechanism for programming or updating those components. The programming method and supported components shall be specified in the corresponding board documentation.

### 2.3 Electrical and Mechanical Compatibility
- **OLY-SYS-006 — Electrical Bus Compatibility:** All boards intended to be compatible with the Olympus platform shall comply with the electrical characteristics, pin assignments, and interface requirements defined in the Interface Control Document.

- **OLY-SYS-007 — Mechanical Compatibility:** All boards intended to be compatible with the Olympus platform shall comply with the mechanical interface specification, including PCB dimensions, mounting-hole positions, connector locations, and stacking clearances.

### 2.4 Electrical Protection
- **OLY-SYS-008 — Electrical Protection:** Each Olympus board shall incorporate appropriate protection mechanisms against short circuits, overvoltage, and overcurrent conditions to prevent damage to the board itself and to other boards connected to the platform. The protection mechanisms shall operate within the electrical limits defined in the ICD. 

- **OLY-SYS-009 — Short-Circuit Protection:** Each Olympus board shall prevent short-circuit conditions within its specified protection scope from causing electrical damage to itself or other connected boards.

- **OLY-SYS-010 — Overvoltage Protection:** Each Olympus board shall tolerate or safely isolate overvoltage conditions within the fault envelope specified for its power and signal interfaces.

- **OLY-SYS-011 — Overcurrent Protection:** Each Olympus board shall limit or interrupt excessive current within its specified protection scope before the applicable electrical safety limits are exceeded

## 3. Processing & Safety Core Requirements (Zeus Board)
- **OLY-ZEUS-001 — Heterogeneous Processing:** The Zeus Board shall incorporate a Rockchip RK3568 SoC as the primary processing unit, paired with an integrated Raspberry Pi RP2350A microcontroller for real-time co-processing and system safety. The board shall support the execution of embedded Linux, real-time operating systems (RTOS), and edge AI inference, subject to hardware feature availability and compatible software stacks.

- **OLY-ZEUS-002 — FPGA Hardware Supervisor:** The Zeus Board shall incorporate a programmable FPGAs dedicated to hardware monitoring, signal processing and fault-management functions. Their internal logic shall be reprogrammable to support alternative implementations and experimental configurations.

- **OLY-ZEUS-003 — FPGA-Based Fault Detection:** The Zeus Board shall provide FPGA-based processing resources for implementing fault-detection algorithms, including AI-based approaches. The architecture shall allow the FPGA logic to be modified to evaluate different detection techniques.

- **OLY-ZEUS-004 — Hardware Signal Filtering:** The Zeus Board shall provide FPGA-based resources for implementing hardware signal-filtering functions independently of the main processing subsystem.

- **OLY-ZEUS-005 — Hardware Health Telemetry:** The Zeus Board shall provide telemetry for monitoring the specified power-supply rails, current consumption, and temperature. The collected measurements shall be accessible to the system monitoring functions.

## 4. Power Unit Requirements (Ares Board)
- **OLY-ARES-001 — Power Distribution:** Regulate external power input and supply stable, filtered voltage rail of `12V` to the Olimpo Backplane.
- **OLY-ARES-002 — Electrical Fault Protection:** Implement overvoltage, overcurrent, reverse polarity and brownout protection mechanisms with interrupt signals routed to the Zeus Board.

**To Be Defined more**

## 5. Vehicle & Motion Interface Requirements (Hephaestus Board)
- **OLY-HEPHAESTUS-001 — Industrial/Vehicle Interfaces:** Provide isolated CAN bus, isolated UARTs and sensor acquisition interfaces for industrial and automotive applications.
- **OLY-HEPHAESTUS-002 — Motion Control Outputs:** Support dedicated PWM and motor control driving interfaces with hardware-level emergency disable inputs.

## 6. Software and Firmware Requirements
- **OLY-SW-001 — Yocto BSP Layer:** Provide an open-source Yocto layer (`meta-olimpo`) for compiling custom Embedded Linux distributions for the RK3568 SoC.
- **OLY-SW-002 — RTOS Integration:** Ensure driver and porting support for Zephyr RTOS or RTEMS on the RP2350 real-time core.
- **OLY-SW-003 — Open FPGA Toolchain Compatibility:** Safety supervisor logic HDL (VHDL/Verilog) must be compatible with open-source FPGA synthesis toolchains where feasible.