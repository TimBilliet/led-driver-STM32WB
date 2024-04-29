# 4 channel LED driver with STM32WB15CC
A RGBW led driver using SY7203 LED driver IC's that can be controlled via an external pwm signal or an STM32WB15CCU6.\
The input source is meant to be a 3S lipo battery.\
Designed for a school project in EAGLE 9.6.0. PCB's manufactured by JLCPCB. Components from LCSC.

## LED power:
P<sub>WHITE</sub> = 3V * 0,714A * 9 = 19,28W\
P<sub>RED</sub> = 2,15V * 0,14A * 8 = 2,41W\
P<sub>GREEN</sub> = 3,1V * 0,14A * 8 = 3,47W\
P<sub>BLUE</sub> = 3,1V * 0,14A * 8 = 3,47W\
P<sub>TOT</sub> = 19,28W + 2,41W + 3,47W + 3,47W = 28,63W

Because of this quite high power an aluminium PCB was used for the LED's. A heatsink and fan were attached to that PCB.

## Driver PCB
![IMG_20240201_095358](https://github.com/TimBilliet/led-driver-STM32WB/assets/47719114/1d00fd39-b65d-4da4-9a5c-01f60e516531)
## LED PCB
![IMG_20240201_095415](https://github.com/TimBilliet/led-driver-STM32WB/assets/47719114/e4385dfa-fca4-4b7d-9c51-47702b609405)
## Mistakes
- Trying to use UART for programming the MCU.I was unable to get it working so i soldered wires to the ST-link pins to program it.
- Not using thermals on the copper pours. It's not a problem when using an oven but manual rework is a pain.
- Forgot to put via's to ground under the MCU. This has since been fixed.
- Using a MLPF-WB-02D3 RF filter on the antenna trace. I was unable to solder this, even in an oven. The pads were way too small for me.
- Using a reverse polarity protection MOSFET with a too low I<sub>D</sub>. When the battery was almost empty the current went up and the MOSFET got very hot.
- When testing the red LED's of the LED pcb i somehow blew them up. (red LED's have the lowest V<sub>f</sub> ....hmm)
