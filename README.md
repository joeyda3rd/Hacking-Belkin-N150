# Hacking-Belkin-N150
Reverse engineering a Belkin N150 Wireless Router model F9K1001V4

# Accessing UART Interface without JTAGulator
1. Remove the board from the case, the first screw is under the sticker on the bottom.
2. Near the Broadcome MCU, you'll find 4 test points at J3 (TP106) - [See image](https://github.com/joeyda3rd/Hacking-Belkin-N150/blob/a3123a9b957c4d2f79572712a6794ddaf572a476/images/20230410_134249.jpg)
3. Using a multimeter, check voltages and resistance against GND and VCC to determine pinout, see chart below.
5. solder a 4 (or 3) pin connector strip through the holes or onto the pads. - [see image](https://github.com/joeyda3rd/Hacking-Belkin-N150/blob/a3123a9b957c4d2f79572712a6794ddaf572a476/images/20230411_114347.jpg)
6. Connect UART serial port adapter (FTDI FT232RL) at 3.3V. GND to GND, cross Tx to Rx and Rx to Tx, 4th pin unused

# Test Point Multimeter Chart
with ethernet ports on the left, point 1 is on the left and 4 is on the far right

| TP | V | Ω GND | Ω VCC | Notes |
|----|---|-------|-------|-------|
| 1  | 0 |||GND|
| 2  |3.3||||
| 3  |3.3||||
| 4  |3.3|||unused|

# Information
Microprocessor: Broadcom BCM5356C0KFBG
