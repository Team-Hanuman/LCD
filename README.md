
# LCD DISPLAY CONTROLLER
## RTL Design and Functional Verification Using Verilog HDL

### A Selection-Based Character Display System Using FSM and Multiplexer

---
---



[Click here to view the Project PDF](content://media/external_primary/file/1000397715)

## 1. Introduction

The LCD Display Controller is designed using Verilog HDL. The main purpose of this project is to display different messages on an LCD.

The design uses a Finite State Machine (FSM), Counter, and Multiplexer to control the LCD operations.

A 2-bit selection input is used to select one of four predefined messages. The selected message is converted into 8-bit ASCII character values and transferred to the LCD.

## 2. Abstract

This project presents an LCD Display Controller implemented using Verilog HDL.

The design consists of two main modules:
- LCD Controller Module
- Message Selection MUX Module

A 2-bit selection input selects one of four predefined messages. The selected message is supplied as eleven 8-bit character values to the LCD controller.

The controller uses a counter-driven FSM to generate the initial delay, perform LCD initialization, and transfer character data through an 8-bit data output.

The Enable (EN) and Register Select (RS) signals are used as LCD control signals.

## 3. Objectives

The main objectives of this project are:

1. To design an LCD controller using Verilog HDL.
2. To generate initialization and data-transfer timing using a counter and FSM.
3. To select one of four predefined messages using a 2-bit selection input.
4. To transfer selected 8-bit character codes to the LCD data bus.
5. To generate Enable and Register Select signals.
6. To verify the RTL design using Vivado simulation.

## 4. System Architecture

The system architecture consists of:

- Clock and Reset inputs
- 2-bit Selection input
- Message Selection Multiplexer
- LCD Controller FSM
- LCD Interface

The selection input controls the message multiplexer. The multiplexer selects one of four messages and sends eleven character bytes (A-K) to the LCD controller.

The LCD controller uses an FSM and counter to process the characters sequentially.

### Block Diagram Working

1. Clock and Reset control the FSM and counter.
2. Selection input selects the required message.
3. Multiplexer provides the selected character data.
4. LCD Controller processes the character bytes.
5. EN, RS, and DATA signals are generated.
6. The LCD interface receives the output signals.

## 5. Message Selection

The 2-bit selection input selects one of four messages.

| Selection Input | Message |
|---|---|
| 00 | HANUMAN |
| 01 | VIBHISHANA |
| 10 | PARASHURAMA |
| 11 | KRIPAVYALI (intended) |

Each message is represented using eleven 8-bit ASCII character positions. Spaces are added wherever required.

## 6. FSM and Timing Sequence

FSM stands for Finite State Machine.

It controls the sequence of operations in the LCD controller.

The supplied RTL uses states from 0 to 17.

### FSM Operations

- State 0: Power-up delay.
- State 1: First LCD initialization pulse.
- State 2: Waiting period.
- State 3: Second initialization pulse.
- State 4: Waiting period.
- State 5: Third initialization pulse.
- State 6: Additional waiting period.
- States 7 to 17: Transfer eleven message characters A to K.

The counter generates the required timing delays.

For each character state, the controller places the corresponding character byte on the command register and controls the Enable signal.

## 7. Design Implementation

The project is implemented using two Verilog modules.

### 7.1 LCD Controller Module

The LCD controller accepts:

- Clock (clk)
- Reset (rst)
- Eleven 8-bit character inputs (A to K)

It generates:

- Enable (en)
- Register Select (rs)
- Data Output (data[7:0])

Internal registers:

- State register: 8-bit
- Command register: 8-bit
- Counter register: 32-bit

The controller performs initialization and transfers the selected message characters sequentially.

### 7.2 Message Selection MUX Module

The Message Selection MUX accepts:

- Clock (clk)
- Reset (rst)
- Selection input (sel[1:0])

Based on the selection input, it assigns the corresponding eleven ASCII character values.

The selected character bytes are connected to the LCD controller.

## 8. Functional Verification

Functional verification is performed using Xilinx Vivado software.

The RTL schematic and simulation waveforms are used to verify the design.

The following operations are checked:

1. Reset operation.
2. LCD power-up delay.
3. LCD initialization sequence.
4. HANUMAN message selection.
5. VIBHISHANA message selection.
6. PARASHURAMA message selection.
7. KRIPAVYALI message selection.
8. Enable, Register Select, and Data signal activity.

## 9. Results

The Vivado RTL schematic shows the synthesized design structure.

### RTL Schematic Results

- Total Cells: 12
- I/O Ports: 14
- Nets: 93

The simulation waveforms show the selection input, Enable signal, Register Select signal, and 8-bit data bus.

The data bus displays ASCII character values corresponding to the selected messages.

These results demonstrate selection-dependent data transfer activity in simulation.

## 10. Applications

1. Text and status display systems.
2. FPGA-based display systems.
3. Embedded systems.
4. Information display boards.
5. Digital electronics laboratory experiments.
6. LCD interface prototyping.

## 11. Future Enhancements

1. Add a complete HD44780-compatible LCD initialization sequence.
2. Improve RS signal control.
3. Add an explicit final state and continuous display operation.
4. Use parameterized clock frequency and timing values.
5. Support a 16-character, 2-line LCD.
6. Add scrolling and dynamic text display.
7. Verify the design using actual FPGA hardware and a physical LCD.

## 12. Conclusion

The LCD Display Controller demonstrates a modular Verilog HDL implementation using a Message Selection Multiplexer and a counter-driven Finite State Machine.

A 2-bit selection input selects one of four predefined messages. The controller transfers eleven 8-bit character values to the LCD interface using Enable and Register Select signals.

The RTL schematic and simulation waveforms provide evidence of the synthesized structure and selection-dependent data-bus activity.

Through this project, we learned about Verilog HDL, FSM design, Counters, Multiplexers, RTL design, and Functional Verification using Vivado.

---

# VIVA QUESTIONS AND ANSWERS

### 1. What is Verilog HDL?
Verilog HDL is a Hardware Description Language used to design digital circuits.

### 2. What is LCD?
LCD stands for Liquid Crystal Display. It is used to display text and information.

### 3. What is FSM?
FSM stands for Finite State Machine. It controls the sequence of operations in a digital system.

### 4. What is a Multiplexer?
A Multiplexer is a digital circuit that selects one input from multiple inputs based on selection lines.

### 5. Why do we use a Counter?
A counter is used to generate delays and control timing operations.

### 6. What is the function of EN?
EN stands for Enable. It controls the data transfer operation of the LCD.

### 7. What is RS?
RS stands for Register Select. It selects between command mode and data mode.

### 8. Why do we use a 2-bit selection input?
A 2-bit selection input provides four possible combinations to select four different messages.

### 9. What is the use of Reset?
Reset initializes the internal registers and outputs to their initial values.

### 10. Which software is used in this project?
Xilinx Vivado is used for RTL design, synthesis, and simulation.

### 11. What is ASCII?
ASCII stands for American Standard Code for Information Interchange. It represents characters using numeric codes.

### 12. What is RTL?
RTL stands for Register Transfer Level. It describes the flow of data between registers.

### 13. What are the outputs of this project?
The outputs are Enable (EN), Register Select (RS), and Data[7:0].

### 14. How many messages are available?
Four predefined messages are available.

### 15. What is the main advantage of this project?
It provides a simple and efficient method to select and display different messages using Verilog HDL.

---

# PROJECT PRESENTATION SPEECH

Good morning everyone.

Today, we are going to explain our project titled LCD Display Controller Using Verilog HDL.

The main objective of our project is to display four different messages on an LCD.

In this project, we use a Multiplexer to select the messages and a Finite State Machine to control the LCD operations.

First, we provide the 2-bit selection input. Based on this input, the multiplexer selects one of the four predefined messages.

Then, the selected character data is transferred to the LCD controller.

The LCD controller uses a counter and FSM to generate timing signals and transfer the characters one by one.

We use Xilinx Vivado software for RTL design and functional verification.

The simulation waveforms show the selected message data and control signal activity.

Finally, this project helps us understand Verilog HDL, FSM, Counters, Multiplexers, and LCD interfacing.

Thank you.
