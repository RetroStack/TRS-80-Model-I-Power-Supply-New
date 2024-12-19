# TRS-80 Model 1 - Power Supply

This project is a reimplementation of the TRS-80 Model 1 Power Supply that replicates the DC and AC voltages needed to run the original system. This revision is based on [previous work](https://github.com/maboytim/TRS-80_Model1_Power_Supply) by Matt Boytim, with slight modifications to that design. The entire project is available under the MIT license, while the reference project has been released into the Public Domain.

This version supports both 120V and 230V.

**NOTE**: A [previous power supply](https://github.com/RetroStack/TRS-80-Model-I-Power-Supply) was released by RetroStack. This new version replaces that power supply as it is cheaper to produce, lighter, and smaller.

**WARNING**: This project involves high voltages that can cause severe injury, death, or property damage. Only proceed if you have the necessary experience and knowledge in handling high-voltage electronics.

- **Safety First**: Always unplug the device and ensure it is fully discharged before beginning any work. Capacitors can store a significant amount of energy. Use insulated tools and wear appropriate safety gear, such as rubber gloves and safety glasses.
- **Risk of Fire and Shock**: Incorrect wiring or assembly can lead to electric shock, fire, or malfunction. Double-check all connections, and if you're unsure, consult a qualified electrician or engineer. As this is a hobby device, never leave it connected without supervision.
- **Use at Your Own Risk**: The creator of this project is not liable for any damage, injury, or harm caused by the misuse of these instructions. Proceed with extreme caution and at your own risk.

![E1 Replica](/Images/Photo.png)

## Project Details

### Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/Gerber_PCBWay.zip) and [JLCPCB](/Latest/Gerber_JLCPCB.zip). Most manufacturers should be fine with either.
- A Bill of Materials (BOM) in both [CSV](/Latest/BOM.csv) and [PDF](/Latest/BOM.pdf) formats. (Also, see the list below.)
- The [full schematics](/Latest/Schematics.pdf).
- 3D Objects (only need base and lid for full assembly):
  - [Base](/Latest/3DPrint_Base.stl)
  - Lid
    - For resin printing: [Lid](/Latest/3DPrint_Lid.stl) and [Plain Lid](/Latest/3DPrint_Lid_Plain.stl)
    - For FPM printing: [Lid](/Latest/3DPrint_Lid_FPM.stl) and [Plain Lid](/Latest/3DPrint_Lid_FPM_Plain.stl)
  - Optional [Label](/Latest/3DPrint_Label.stl): Saves on printing suport with FPM or enables printing a badge for plain models

### Bill of Materials (BOM)

| Reference | Qty | Value      | Footprint                                                   | Source                                                                                                                 |
| --------- | --- | ---------- | ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| C1,C2     | 2   | 2200u      | Capacitor_THT:CP_Radial_D12.5mm_P5.00mm                     | [Mouser](https://www.mouser.com/ProductDetail/647-UVR1C222MHD1TO)                                                      |
| D1        | 1   | B40C800G   | Diode_THT:Diode_Bridge_Round_D9.8mm                         | [Mouser](https://www.mouser.com/ProductDetail/625-B40C800G-E4)                                                         |
| T1        | 1   |            | ST-6-16 (110V) or DST-6-16 (220V)                           | Mouser [ST](https://www.mouser.com/ProductDetail/530-ST-6-16) [DST](https://www.mouser.com/ProductDetail/530-DST-6-16) |
| -         | 1   | Power Unit | With Fuse, Switch and C8 connector                          | [AliExpress](https://www.aliexpress.us/item/3256805889410008.html)                                                     |
| -         | 1   | Case       | Top                                                         | [JLCPCB](https://jlc3dp.com/3d-printing-quote)                                                                         |
| -         | 1   | Case       | Bottom                                                      | [JLCPCB](https://jlc3dp.com/3d-printing-quote)                                                                         |
| -         | 2   | M3         | Screw; 40mm length or longer (for Transformer); Sunken Head |                                                                                                                        |
| -         | 2   | M3         | Nut (for Transformer)                                       |                                                                                                                        |
| -         | 4   | M3         | Screw; 10mm length (for Case); Sunken Head                  |                                                                                                                        |
| -         | 2   | M3         | Screw; 6mm length (for power unit); Black                   |                                                                                                                        |
| -         | 1   | 6N-4       | Strain Relief                                               | [AliExpress](https://www.aliexpress.us/item/3256804453313992.html)                                                     |
| -         | 1   | Cable      | 4 or 5-wires (5 preferred); ~50cm length                    |                                                                                                                        |
| -         | 1   | DIN-5      | Connector                                                   |                                                                                                                        |
| -         | 1   | Zip-Tie    | To improve strain relief                                    |                                                                                                                        |
| -         | 1   | Fuse       | 1.5A 250V; 6x30mm Glass Fuse; Fast Blow                     |                                                                                                                        |
| -         | -   | Wire       | AWG 20 (or lower) for power connection                      |                                                                                                                        |

### Assembly

**Prepare Case**

1.  3D print the case (lid and base) or order it from a manufacturer.
2.  a. If 3D printed with PLA or similar material, use a soldering iron to set the knurled nuts. You can purchase a set of tools to simplify this, but a soldering iron is sufficient.

    b. If 3D printed with resin, set the knurled nuts with super glue or similar. Be careful not to cover the threads with glue, as this will cause problems when screwing things in later on. Wait until the glue is fully set before moving on.

![3D Case](/Images/3DPrint_Top.png)

4. Paint the lettering on the top. I achieved good results using a foam brush or Q-tip. Optionally, apply a clear coat to protect the paint from wearing off.
5. (Optional) If the label object is printed with a plain lid, simply glue the label on top of the lid.

**Electronics**

1. Solder in the transformer. Match the numbers written on the terminals to the numbers on the PCB. If you're using the ST-6-16, terminals 2 and 3 will be missing, which is fine. These are only used for the DST-6-16.
2. Solder in the two capacitors. They are polarized, so ensure the negatively marked sides match the PCB silkscreen.
3. Solder in the rectifier, aligning the direction with the PCB silkscreen.
4. Solder a 5-wire cable to the secondary side of the transformer, between the capacitors. Ideally, match a red wire to the center (~20V DC), a green/yellow wire to the outer AC connections, and a black/white wire to the two positions adjacent to the center (for ground). Matching colors or jotting down the wire colors will help you later when soldering the DIN-5 connector. You can also use a 4-wire cable, but in that case, choose only one ground pad instead of both.
5. _(Optional)_ Add a cable tie around the cable for extra strain relief.

![Open](/Images/Open.png)

6. Crimp two short wires to create jumpers: one between the terminal and the switch, and another from the fuse to the switch. Connect the first wire (from the connector, not the fuse) to the switch's common terminal, which is usually marked with a different color. One side of the switch will be for the light (you can typically see the lightbulb leads). Use the opposite side so the light turns on only when the switch is activated. If it's incorrect, you can swap them later. I used AWG 20 wire for this.
7. Crimp two more wires on one side, each connecting to the other side of the switch and carrying the 110V/220V AC. I used AWG 20 wire. Depending on your power unit (see below), different connections may be required.

![Power Unit](/Images/Power_Unit2.png)

**NOTE:** There are different configurations for the power unit. Here’s another setup I've used in the past:

![Power Unit](/Images/Power_Unit1.png)

8. Solder the last two wires into place on one side of the PCB (the primary side). Leave them disconnected from the power unit for now.
9. Screw in the transformer and PCB using long M4 screws and nuts.
10. Screw in the power unit. First, pull out the two crimped cables and connect them to the remaining terminals on the power unit before screwing it in.
11. Assemble the case using the smaller M3 screws.
12. Add the plastic grommet for strain relief.

![Strain Relief Open](/Images/Strain_Relief1.png)
![Strain Relief Closed](/Images/Strain_Relief2.png)

13. Solder the DIN-5 connector according to this diagram:

![PCB](/Images/DIN-5_Connector.png)

14. Insert the fuse into the fuse holder.

### Implementation

The project has been implemented using KiCAD 8. The KiCAD project files are included in this repository.

![Front](/Images/3D_Front.png)
![Back](/Images/3D_Back.png)

### 3D Objects

The project includes various types of 3D objects for self-printing. It offers a set of bases and lids for resin prints, where the screw inserts must be glued in place, while the FPM version features slightly smaller holes designed for heat setting. Additionally, plain lids with separate label objects are provided, allowing the label and lid to be printed separately. This reduces the need for supports and enhances overall print quality.

![PCB](/Images/3DPrint_Overview.png)

### RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Main TRS-80 Model 1 Repository

For additional resources related to the TRS-80 Model 1, be sure to check out the central page for the TRS-80 Model 1 on RetroStack. You can find it [here](https://www.github.com/RetroStack/TRS-80-Model-I).

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. My work involves creating detailed documentation and videos to share the knowledge. I am also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, I invite you to visit my [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
