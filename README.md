# TRS-80 Model 1 - Power Supply

This project is a reimplementation of the TRS-80 Model 1 Power Supply that replicates the DC and AC voltages needed to run the original system. This revision is based on [previous work](https://github.com/maboytim/TRS-80_Model1_Power_Supply) by Matt Boytim, with slight modifications to that design. The entire project is available under the MIT license, while the reference project has been released into the Public Domain.

This version supports both 120V and 230V.

**NOTE**: A previous power supply was released by RetroStack. This new version replaces that power supply as it is cheaper to produce, lighter, and smaller.

**WARNING**: This project works with high voltages. Please proceed only if you are experienced with handling high-voltage electronics. Working on high voltages can be fatal and, if done incorrectly, could cause a fire or damage to property.

![E1 Replica](/Latest/Photo.png)

## Project Details

### Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/Gerber_PCBWay.zip) and [JLCPCB](/Latest/Gerber_JLCPCB.zip). Most manufacturers should be fine with either.
- A Bill of Materials (BOM) in both [CSV](/Latest/BOM.csv) and [PDF](/Latest/BOM.pdf) formats. (Also, see the list below.)
- The [full schematics](/Latest/Schematics.pdf).
- 3D Objects of [Base](/Latest/3DPrint_Base.stl) and [Lid](/Latest/3DPrint_Lid.stl) for 3D printing.

### Bill of Materials (BOM)

| Reference | Qty | Value    | Footprint                               |
| --------- | --- | -------- | --------------------------------------- |
| C1,C2     | 2   | 2200u    | Capacitor_THT:CP_Radial_D12.5mm_P5.00mm |
| D1        | 1   | B40C800G | Diode_THT:Diode_Bridge_Round_D9.8mm     |
| T1        | 1   | DST-6-16 | M1PSX3:XFMR_DST-6-16                    |

### Assembly

**Prepare Case**

1. 3D print case (lid and base) or order from manufacturer.
2. (a) If 3D printed with PLA and similar, use a soldering iron to set the knurled nuts. You can buy a set of tools to simplify this, but a soldering iron is enough.
3. (b) If 3D printed with resin, drill out a bit more space on all the 6 places and set the knurled nuts with super glue. Make sure to not cover the threads as it would give you trouble later to screw things in. Wait for it to get really solid before moving on.

![3D Case](/Images/3DPrint_Model.png)

4. Paint the lettering on the top. I was able to do this nicely with a foam brush. Optionally add a clear coat to protect the paint from rubbing off.
5. Screw in the transformer with the M4 screws.

**Electronics**

1. Crimp two short wires to add a jumper between the neutral to the switch and another from the fuse to the switch. One side of the switch will be the terminals of the light (you can often see the leads for the lightbulb). You want the one side not for the light so the light only turns on when switch is turned on. You can swap them around later if you find it isn't correct. For the wire, I used AWG 26.

![Power Unit](/Images/Power_Unit.png)

2. Crimp two more wires on one side, each connecting to ther other side of the switch and carrying the 110V AC. For the wire, I used AWG 26.
3. Solder the last two wires into place on the side of the transformer with only two terminals. This is the primary side.
4. Solder 6 wires to the secondary side of the transformer. Make sure that each wire can reach to the PCB area.
5. Add the two diodes on the PCB. Make sure to put them into the correct direction as indicated on the PCB and the line on the diodes. Both diodes are oriented in the same direction.
6. Solder all 6 wires to the PCB sequentially as shown. First, SA# are the top 3 terminals from left to right. Second, SB# are the bottom 3 terminals from left to right.

![PCB](/Images/PCB_Overview.png)

7. Solder the two AC wires (marked "~") from the cable going to the computer. Confirm that these are the right wires with the graphic shown below.
8. Solder the two other wires (marked "+" and "-") from the cable going to the computer. Confirm that these are the right wires with the graphic shown below.

![PCB](/Images/DIN-5_Connector.png)

9. (optional) Add some glue to add some kind of strain relief on the wires themselves.
10. (optional) Add a cable-tie around the cable to add an additional way of strain relief.
11. Finally, add the plastic grommet which is used as the main method of strain relief.
12. Screw in PCB
13. Screw in Power Unit
14. Screw the lid to the top
15. Add fuse to the fuse holder

### Implementation

The project has been implemented using KiCAD 8. The KiCAD project files are included in this repository.

![Front](/Latest/3D_Front.png)
![Back](/Latest/3D_Back.png)

### RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Main TRS-80 Model 1 Repository

For additional resources related to the TRS-80 Model 1, be sure to check out the central page for the TRS-80 Model 1 on RetroStack. You can find it [here](https://www.github.com/RetroStack/TRS-80-Model-I).

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. My work involves creating detailed documentation and videos to share the knowledge. I am also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, I invite you to visit my [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
