4-Bit Microprocessor Architecture in Verilog
Project Overview
This repository contains a structural implementation of a 4-bit microprocessor designed in Verilog. The goal of this project was to model a functional Von Neumann-inspired architecture from the ground up, focusing on the relationship between a central control unit and its peripheral memory and logic components.
By breaking the system down into modular blocks, the design maintains a clear separation between data processing and control logic, making it easier to scale or debug individual hardware components.

System Architecture
The design is comprised of four primary functional modules:

1. Arithmetic Logic Unit (ALU)
The ALU serves as the computational engine of the processor. It is designed to handle fundamental arithmetic operations such as addition and subtraction, alongside bitwise logical operations (AND, OR). These operations are triggered by control signals decoded from the instruction register.

2. Instruction Memory (ROM)
The ROM acts as a dedicated storage space for the program code. It holds an 8-bit instruction format where the upper nibble defines the opcode and the lower nibble serves as the operand or memory address.

3. Data Memory (RAM)
The RAM provides 16 addressable storage locations, each 4 bits wide. This module supports synchronous write operations and asynchronous reads, allowing the CPU to store intermediate calculation results during program execution.

4. CPU Core & Control Unit
The Core acts as the system coordinator. It implements a synchronous Fetch-Execute state machine. During the Fetch cycle, the processor retrieves instructions and increments the Program Counter. During the Execute cycle, it decodes instructions to orchestrate data flow between the Accumulator, the ALU, and the RAM.

Supported Instruction Set

The processor currently supports a streamlined Instruction Set Architecture (ISA) designed for efficient execution:
* LDI (Load Immediate):** Directly loads a 4-bit constant into the accumulator.
* STA (Store Accumulator):** Saves the current accumulator value to a specified RAM address.
* ADD (Addition):** Adds a value from a specific RAM location to the accumulator using the ALU.
* HLT (Halt):** Terminates program execution and stabilizes system signals.

Technical Objectives
This project was developed to explore hardware description languages (HDL) and digital logic design. The implementation emphasizes timing accuracy, proper signal routing, and the fundamental mechanics of a fetch-decode-execute pipeline.
