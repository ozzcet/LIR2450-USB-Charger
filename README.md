# LIR2450 USB Charger

**Warning:** The board arrived and the circuit does charge coin cells but the led indicator for a full charge does not work. Currently I don't know why. Any hints are appreciated.

I started doing a lot with low power devices (Arduino, BLE 4.0) and coin cells are a convenient power source. Lately I found out that there are even rechargeable coin cells. That's why I needed a charger. There are only a few models out there which are either expensive or have a charge current that I think is to high. So I made my own.

![3D-Model](3D-Model/3D-Model_bothSides.jpg?raw=true)
[3D-Model on Sketchfab](https://sketchfab.com/models/f6b9f5c950564a3f85bb46c3d435a189)

It is based on the [MCP73831](https://www.sparkfun.com/datasheets/Prototyping/Batteries/MCP73831T.pdf). 
Order three PCBs for 13.60$ at OSHPARK: [LIR2450 USB Charger](https://oshpark.com/projects/roORU8h6)

There are two charge modes:
 
- fast (45mA)
- slow (25mA)

Max charge current for a coin cell is usually between 80% and two third of it's capacity. So you could charge a 100mA coin cell with 80mA. I wanted to increase the lifetime of my coin cells and reduced the charge current. If you want to have different currents here is the equation to calculate R_SLOW/R_FAST:

`mA = 1000 / R in kΩ`

Example: 1000/20kΩ = 50mA

## PCB height vs USB port

The PCB is usually only 1.6mm thick which means another 0.8mm are needed so that this PCB fits nicely into a USB port without falling out. That means you need to tin the USB connector which might gain you another 0.4mm and then add some ducktape or paper to the backside until the USB connector is around 2.4mm in height.

## BOM

- MCP73831 SOT-23-5
- 0603 LED Green (~3.1V voltage drop)
- 0603 LED Orange (~2V voltage drop)
- 0805 Resistor 200Ω
- 0805 Resistor 320Ω
- 0805 Resistor 40kΩ
- 0805 Resistor 22kΩ
- 2x 0805 Capacitor 4.7uF
- CR/LIR2450 Coin cell holder (20mm diameter, 5mm height)
- (optional) male pin header, jst pin header

## Schematics

Checkout `PCB-Masks` folder if you want to etch it on your own.

![Schematics](Schematics.png?raw=true)
![PCB-Overview](OverviewBoard.png?raw=true)
