---
project: uart-over-midi
stars: 10
description: null
url: https://github.com/shapoco/uart-over-midi
---

UoM: UART over MIDI
===================

Overview
--------

A protocol for transferring arbitrary byte sequences using MIDI.

Protocol
--------

### Basic Packet Format

### Payload Encoding

### Control Code Definition and Payload Format

### Error Codes

Code

Mnemonic

Description

0

UOM\_OK

No Error

1

UOM\_ERR\_MIDI\_RX\_BUFF\_OVFL

MIDI Message Too Long

2

UOM\_ERR\_MIDI\_INVALID\_MSG

Invalid MIDI Message

3

UOM\_ERR\_INVALID\_MARKER

Invalid UoM Marker

4

UOM\_ERR\_SYNTAX

Invalid UoM Packet Format

5

UOM\_ERR\_INVALID\_PARAM

Invalid Parameter

6

UOM\_ERR\_INVALID\_CTL\_CODE

Unknown Control Code

7

UOM\_ERR\_NO\_FUNCTION

Function Not Supported

* * *
