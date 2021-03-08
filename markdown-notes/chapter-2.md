# Chapter 2

## 2-1 Serial Communications

Micro controllers transfer data in two ways: **parallel** and **serial**

- parallel: several data bits are transferred simultaneously
- serial: a single data bit is transferred at one time

Advantages of serial communication

- longer distances
- easier to synchronize
- fewer I/O pins and lower cost

Serial communication often requires

- **shift registers**: convert a byte to a serial bits and vice versa
- **modems**: modulate/demodulate serial bits to/from audio tones

## 2-2 Serial Communication Terminology

### Asynchronous versus Synchronous

- Synchronous serial communication
  - the clocks of the sender and receiver are synchronized
  - a clock of characters, enclosed by synchronizing bytes, is sent at a time
  - faster transfer and less overhead
- Asynchronous serial communication
  - the clocks of the sender and receiver are not synchronized
  - one character is sent at a time, enclosed between a start bit and one or two stop bits, a parity bit may be included

### Baud Rate

Data transmission rates are typically specified as a **baud** or bits per second rate

### Full Duplex

A **single duplex** system has a single complement of hardware that must be switched from transmission to reception configuration

A **full duplex** serial communication system has separate hardware for transmission and reception

### Nonreturn to Zero Coding Format

The ATmega16 uses a **nonreturn to zero coding** standard, coding a logic 1 is signaled by a logic high during the entire time slot allocated for a single bit, whereas a logic 0 is signaled by a logic low during the entire time slot allocated for a single bit.

### RS-232 Communication Protocol

The RS-232 is a widely used standard for serial interfacing, which covers four main aspects

- Electrical: voltage level, rise and fall time, data rate and distance
- Functional: function of each signal
- Mechanical: number of pins, shape and dimension of connectors
- Procedural: sequence of events for transmitting data

| Logic | RS-232 Levels |  TTL Levels  |
| :---: | :-----------: | :----------: |
|   1   | $[-15V,-3V]$  | $[+2V,+5V]$  |
|   0   | $[+3V,+15V]$  | $[0V,+0.8V]$ |

### Parity

- Parity Bit: a single bit for error checking, sent with data bits to make the total number of 1's
- Start Bit: the **indication** of the start of a character
- Stop Bit: the **indication** of the end of a character

## 2-3 Serial USART

### Hardware Elements

There are mainly **four** basic pieces in USART

- the clock generator
- the transmission hardware
- the receiver hardware
- three control registers (USARTA, USARTB and USARTC)

#### Clock Generator

- provide clock source
- set **baud rate** using UBRR register

#### Transmitter

- send a character through **TxD** pin
- handle start/stop bits and parity bit, and shift register

#### Receiver

- receive a character through **RxD** pin
- perform the reverse operation of the transmitter

#### Registers

- configure, control and monitor the serial USART

### Registers

#### Baud Rate Registers

UBRRH and UBRRL