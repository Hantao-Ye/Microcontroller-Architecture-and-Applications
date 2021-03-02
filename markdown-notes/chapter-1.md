# Chapter 1 AVR Architecture Overview

## 1-1 Introduction

### AVR Classifications

- Classic AVR
- **Mega AVR**
- Tiny AVR
- Special purpose AVR

<div align = center><img height = 300 src = "../assets/ch1-1.png"></div>

### AVR Features

- an 8-bit **RISC**[^1] micro controller with *Harvard Architecture*[^2]
- high performance with low power
- has a CPU
- has program ROM, RAM, EEPROM, Timers and I/O ports
- owns ADC and PWM
- owns serial interfaces: USART, SPI, TWI, etc

## 1-2 ATmega16 Architecture Overview

### RISC Architecture

- **131** RISC-type instructions
- **32** general purpose 8-bit registers
- operates at a clock speed of **16 MHz** or handles 16 million instructions per second

### Assembly Language Instruction Set

- the most efficient and fast execution for a particular micro controller
- need to be familiar with the low-level architecture details of the controller
- C language is easier to read and transfer

### ATmega16 Architecture Overview

<div align = center><img src = "../assets/ch1-2.jpg"></div>

- a timer subsystem
- a communication system
- an interrupt subsystem
- an analog-to-digital converter (ADC)
- memory components

#### Pins

- four 8-bit ports
- connections for power supplies (VCC/GND/AVCC/AREF)
- external time base input pins (XTAL1/XTAL2)
- processor reset
