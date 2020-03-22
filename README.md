# BBB DB25 CNC Cape
###### Simple Machinekit CNC Cape for Beaglebone Black

--

### /!\ NOT TESTED YET, stay tuned /!\

You'll find here the project files for a simple CNC-oriented Beaglebone Black Cape for a Machinekit setup.

This cape breaks out most of the 'free' I/Os of the BBB:

- 17 with 5V level shifters capable of up to 32mA source/sink (TI SN74LVC1T45) ;
- 17 directly routed to the BBB I/Os (3V3 max).

The 17 5V I/Os are routed to a 2-rows 26-pin header for HE10-like flat cable connection directly to a DB25 port (the 26th pin, not present on DB25 connectors, is 5V power).

The other 3V3 I/Os are here for possible expansions, **but they are not 5V tolerant!**

Project files are Circuit Studio. I may add Circuit Maker files when possible.

---
### BBB DB25 CNC Cape

I/O direction can be selected by the jumpers header, either with jumpers or by soldering a wire. Jumper present = input, otherwise it is an output. If either the 3V3 or the 5V supply of the level shifter is not present, the outputs are high impedance and there is no pull resistors.

The extension connector has 5V and 3V3 power from the BBB. The 2 extra pads next to the extension connector can be manually wired to P9-41 and P9-42 (red dotted lines on the image below) if you want 2 extra I/Os on that connector.

The Cape can be assembled by JLCPCB SMT service. Use the files in ```BBB DB25 CNC Cape/Fab```. Only the bottom side has components. Headers and connectors cannot be assembled by JLCPCB, you'll need a 26-pin header and a 20-pin header for the extension if you want it.

For 5V power input, there is space to a 5.08mm screw terminal or a 3.5mm plug-in terminal. It powers the BBB and possible extensions.

Pads with the white silkscreen are the one used by the cape (including the extension).



![BBB DB25 CNC Cape](https://github.com/GIPdA/BBB-DB25-CNC-Cape/raw/master/BBB%20DB25%20CNC%20Cape/bbb_db25_cnc_cape%20wires.png)

![BBB DB25 CNC Cape](https://github.com/GIPdA/BBB-DB25-CNC-Cape/raw/master/BBB%20DB25%20CNC%20Cape/bbb_db25_cnc_cape%20bottom.png)

---
### BBB DB25 Terminals Extension

This is a PCB to break out the 26-pin HE10 connector to plug-in 3.5mm terminals (horizontal or vertical) in either one PCB or a stackup.

There is two rows of 4 connectors: top row is meant for step/dir outputs (2 I/Os + GND + 5V) with horizontal or vertical terminals. Bottom row is meant for limit switchs, enable and such, with vertical terminals.
The 5-pin terminal is linked to the encoder B input of the BBB.

The bottom row can be stacked up on another PCB to use horizontal terminals if needed (```bbb_db25_terminals_extension_top```).

Gerbers and other fab files are in folders ```bbb_db25_terminals_extension``` and ```bbb_db25_terminals_extension_top```.

![Terminals Extension](https://github.com/GIPdA/BBB-DB25-CNC-Cape/raw/master/BBB%20DB25%20Terminals%20Extension/bbb_db25_terminals_extension.png)

![Terminals Extension Top](https://github.com/GIPdA/BBB-DB25-CNC-Cape/raw/master/BBB%20DB25%20Terminals%20Extension/bbb_db25_terminals_extension_top.png)

--
### Pinout tables

| DB25  | BBB I/O | HE10 Connector      |                 |
|-------|---------|---------------------|-----------------|
| IO1   | P8_26   | 1                   |                 |
| IO2   | P8_19   | 3                   |                 |
| IO3   | P8_18   | 5                   |                 |
| IO4   | P8_17   | 7                   |                 |
| IO5   | P8_16   | 9                   | Encoder 2 Index |
| IO6   | P8_15   | 11                  |                 |
| IO7   | P8_14   | 13                  |                 |
| IO8   | P8_13   | 15                  |                 |
| IO9   | P8_12   | 17                  | Encoder 2 A     |
| IO10  | P8_11   | 19                  | Encoder 2 B     |
| IO11  | P9_23   | 21                  |                 |
| IO12  | P9_26   | 23                  | PRU 1-16 (in)   |
| IO13  | P9_25   | 25                  | PRU 0-7         |
| IO14  | P9_28   | 2                   | PRU 0-3         |
| IO15  | P9_27   | 4                   | PRU 0-5         |
| IO16  | P9_30   | 6                   | PRU 0-2         |
| IO17  | P9_31   | 8                   | PRU 0-0         |
| GND   | GND     | 10                  |                 |
| GND   | GND     | 12                  |                 |
| GND   | GND     | 14                  |                 |
| GND   | GND     | 16                  |                 |
| GND   | GND     | 18                  |                 |
| GND   | GND     | 20                  |                 |
| GND   | GND     | 22                  |                 |
| GND   | GND     | 24                  |                 |
| 5V    | 5V      | 26                  |                 |


|       | BBB I/O | Extension Connector |
|-------|---------|---------------------|
| EXT1  | P8_8    | 1                   |
| EXT2  | P8_10   | 2                   |
| EXT3  | P8_7    | 3                   |
| EXT4  | P8_9    | 4                   |
| GND   | GND     | 5                   |
| EXT5  | P9_24   | 6                   |
| EXT6  | P9_22   | 7                   |
| EXT7  | P9_21   | 8                   |
| EXT8  | P9_18   | 9                   |
| EXT9  | P9_17   | 10                  |
| EXT10 | P9_16   | 11                  |
| EXT11 | P9_15   | 12                  |
| EXT12 | P9_14   | 13                  |
| EXT13 | P9_13   | 14                  |
| EXT14 | P9_12   | 15                  |
| EXT15 | P9_11   | 16                  |
| EXT16 | (P9_41) | 17                  |
| EXT17 | (P9_42) | 18                  |
| 5V    | 5V      | 19                  |
| 3V3   | 3V3     | 20                  |