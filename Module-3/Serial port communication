# Serial Port Terminal Application

## General Communication Arrangement

The general communication arrangement is:

```text
                 Serial Data
┌──────────────┐ ───────────────────► ┌───────────────┐
│              │                      │               │
│    STM32     │                      │      PC       │
│  UART/USART  │ ◄─────────────────── │ Serial        │
│              │     Serial Data      │ Terminal      │
└──────────────┘                      └───────────────┘
```

The STM32's USART/UART peripheral handles serial communication, while the terminal application on the PC displays the data.

## How Does It Work?

The communication takes place in the following steps:

### Step 1 – Configure USART

The USART peripheral of STM32 is configured with parameters such as:

- Baud rate
- Data bits
- Stop bits
- Parity
- Transmission mode

#### Baud Rate

Baud rate represents the rate at which symbols are transmitted through the serial communication channel.

Common values:

- 9600
- 19200
- 38400
- 57600
- 115200

For example, 115200 baud means the communication is configured for 115200 symbols per second under the usual UART binary signaling assumptions.

#### Data Bits

The number of bits used to represent each character.

Commonly:
- 7 bits
- 8 bits

Most embedded applications use 8 data bits.

#### Parity

Parity is used for simple error detection.

Types:
- Even parity
- Odd parity
- No parity

Example: 8N1

- 8 → 8 data bits
- N → No parity
- 1 → 1 stop bit

#### Stop Bits

A stop bit indicates the end of a transmitted character/frame.

Usually:
- 1 stop bit
- 2 stop bits

#### Example Configuration

| Parameter | Value |
|---|---|
| Baud Rate | 115200 |
| Data Bits | 8 |
| Parity | None |
| Stop Bits | 1 |

This is commonly written as:

**115200 8N1**

### Step 2 – Connect STM32 to PC

The STM32 board is connected to the computer using a USB connection or USB-to-UART interface.

```text
STM32 Board
     |
     | USB
     v
  Computer
     |
     v
Serial Terminal
```

### Step 3 – Select COM Port

The terminal application detects a serial port such as:

- COM3
- COM4
- COM5

The correct COM port must be selected.

### Step 4 – Set Communication Parameters

The same settings must be used on both sides.

Example:

| Parameter | Value |
|---|---|
| Baud Rate | 115200 |
| Data Bits | 8 |
| Parity | None |
| Stop Bits | 1 |
| Flow Control | None |

### Step 5 – Send and Receive Data

Suppose STM32 wants to send **HELLO**.

The data is converted into serial bits.

```text
       STM32
         |
         | H
         | E
         | L
         | L
         | O
         v
     Serial Bits
         |
         v
      Computer
         |
         v
   Serial Terminal
```

The terminal converts the received serial data back into characters and displays:

```text
HELLO
```

In STM32, USART can be used for serial communication.

## Basic Connection Between STM32 and PC

```text
STM32                         PC
-----                         --
TX  ────────────────────────► RX
RX  ◄──────────────────────── TX
GND ───────────────────────── GND
```

- TX (Transmit) of STM32 is connected to RX (Receive) of the PC-side USB-to-UART interface.
- RX (Receive) of STM32 is connected to TX (Transmit) of the PC-side USB-to-UART interface.
- GND is connected to GND to provide a common ground reference.
