# Quiz

## Chapter 1

Q1: How many bits in Atmega16 controller?
A: 8

Q2: AVR could be classified into
A: mega, tiny, classic, special-purpose

Q3: The ATmega16 contains
A: timer subsystem, interrupt subsystem, communication subsystem, ADC and memory components

Q4: The ATmega16 is equipped with memory components of
A: In-system Programmable Flash EEPROM, Byte-Addressable EEPROM, Static Random Access Memory

Q5: How many PORTs in Atmega16?
A: 4, A, B, C and D

Q6: How many relevant 8-bit registers for each port?
A: 3, PORTx, PINx, DDRx

Q7: How to configure Data Direction Register as a specific port pin as output
A: DDRxn = 1

Q8: Data Register (PORTx) is used to _____ data.
A: write

Q9: Register Input Pin Address (PINx) is used to _____ data.
A: read

Q10: If PORTxn is written logic _____, the port pin is driven high.
A: 1

Q11: How many timers/counters in ATmega16?
A: 3, 1 16-bit timer and 2 8-bit timers

Q12: How many PWM channels in ATmega16?
A: 4

Q13: How many serial communication subsystems in ATmega16?
A: 3, USART, SPI and TWI

Q14: How many channels is the Atmega16 equipped?
A: 8

Q15: How many interrupt sources in ATmega16?
A: 21, 3 for external and 18 from internal

Q16: What is the resolution of ADC in ATmega16?
A: 10-bit

Q17: In ATmega16, fixed clock operating frequency is 
A: 1, 2, 4 and 8

Q18: What are serial communication subsystems?
A: USART, SPI, IIC

Q19: Write a program to lighten the LED as the button is clicked.

## Chapter 2

Q1: ASCII is a standardized _____-bit method of encoding alphanumeric data
A: 7

Q2: RS232 Communication Protocol is a _____ communication
A: serial

Q3: What is the voltage levels of RS232 to logic 1 and 0
A: logic 1: [−15,−3], logic 0: [3,15]

Q4: There are ____ main tasks when using the serial port
A: 3, initialization, transmission and reception

Q5: USART mainly consists of  _____ basic pieces
A: 4, the clock generator, transmission hardware, receiver hardware and three control registers (UCSRA, UCSRB, UCSRC), two baud rate registers (UBRRH, UBRRL) and one data register (UDR)

Q6: What does the serial communication often require?
A: shift registers and modems

Q7: The transfer of data using parallel lines is _____ (faster/slower) but _____ (more expensive/less expensive)
A: lower, less expensive

Q8: Sending data from a radio station is duplex. True or False?
A: False, it is simplex since the listener could only receive the message sending from the radio.

Q9: In full duplex we must have two data lines, one for transfer and one for receive. True or False?
A: True

Q10: The start and stop bits are used in the _____ (synchronous/asynchronous) method
A: asynchronous

Q11: Assuming that we are transmitting the ASCII letter "E" (0100 0101) in binary with no parity bit and one stop bit, show the sequence of bits transferred serially.
A: 0(start bit)->1->0->1->0->0->0->1->0->1(stop bit)

Q12: Which register is monitored for sending(transmitting) data
A: UDRE

Q13: Which register is monitored for receiving data
A: RXC

Q14: What is the definition of the baud rate?
A: the sending rate of the bytes

Q15: How to configure the register in USART to the specific baud rate?
A: configure the UBRRL and UBRRH with the value of f_OSC/(16⋅BAUD)−1 for asynchronous normal mode and change 16 to 8 if in asynchronous double speed mode and 16 to 2 if in synchronous master mode 

Q16: How to configure the register such that the USART would send data in 7-bit, double speed, asynchronous, 2 sop bit and even parity at 9600 baud rate
A:

```C
u16 myUBRR = F_CPU/(16*9600)-1;
UBRRL = (u8)(myUBRR);
UBRRH = (u8)(myUBRR>>8);

UCSRA = (1<<U2X);
UCSRB = (1<<TXEN) ;
USCRC = (1<<7)|(0<<UMSEL)|(1<<UPM1)|(1<<USBS)|(1<<UCSZ1);
```

Q17: How many wires in SPI
A: 4, MOSI, MISO, SCK(Serial Clock) and ¯SS(slave select)

Q18: How many registers are in SPI
A: 3, SPSR, SPCR and SPDR

Q19: In comparison between USART and SPI, which one is faster?
A: SPI

Q20: Which register in SPI is used to monitor the sending/receiving data?
A: SPIF

Q20: How many wires in TWI?
A: 2, SDA and SCK

Q21: Write a program of USART initialization, transmission and reception.

Q22: Write a program of SPI initialization, transmission and reception.
 
