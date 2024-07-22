# Wireless-Charybdis-Mini-3x6-Build-Guide

![pmw3610_pcb](./images/white_keys.png "Component Placement")

# Intro

This repository is a comprehensive build guide for the Charybdis keyboard, which is an open source, ergonomic keyboard created by [Bastard Keyboards](https://github.com/Bastardkb/Charybdis) and graciously shared with the community.

This guide is a log of all the steps I took in my build process, and for the most part is just a long winded version of Eren Atas' [supremely helpful build guide](https://github.com/erenatas/charybdis-wireless-3x6/blob/master/README.md).

**Join the Community**

For any questions, clarifications, or simply to connect with fellow Charybdis builders, feel free to join the Bastard Keyboards [Discord community](http://www.bstkbd.com/discord).

**Disclaimer**

This guide serves as a resource to assist you in building your Charybdis. I assume no responsibility for any damages or malfunctions that may occur during the build process.

# Build Guide

## Bill of Materials

These are all the components that need to be ordered to build the keyboard.

### PCBs

| **Part**                                                                                                 | **Quantity** |
| -------------------------------------------------------------------------------------------------------- | ------------ |
| [PMW3610 Breakout](https://github.com/victorlucachi/charybdis-pmw3610-breakout/tree/nicenano/production) | 1            |
| [Nano Holder](https://github.com/olidacombe/Elite-C-holder/tree/nicenano/adapter/production)             | 1            |
| [Thumb Right (0.8 thickness)](https://github.com/Bastardkb/Charybdis-PCB-thumbs/releases/tag/2.01)       | 1            |
| [Thumb Left (0.8 thickness)](https://github.com/Bastardkb/TBK-Mini-PCB-thumb-cluster/releases/tag/2.1)   | 1            |
| [Plate (0.8 thickness)](https://github.com/Bastardkb/TBK-Mini-PCB-plate/releases/tag/2.21)               | 1            |


I ordered the PCBs from [JLCPCB](https://jlcpcb.com/).

:warning: **A thickness of 0.8 or less** must be set for the left thumb, right thumb, and plate PCBs.

The gerber files have all been pulled from other repositories and are stored in the PCB Gerber Files directory. However, each source repository is linked in the part list above for reference.

:information_source: An alternative to victorlucachi's PMW3610 breakout design linked above is the [sensor board designed by Bastard Keyboards](https://docs.bastardkb.com/help/bluetooth.html#sensor).

### 3D Case Prints

| **Part**                                                                                                                         | **Quantity** |
| -------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| [Right Plate](https://github.com/Bastardkb/Charybdis/blob/3908164/files/3x6%20mini/plate_v1_v11.stl)                             | 1            |
| [Left Plate](https://github.com/erenatas/charybdis-wireless-3x6/blob/master/3d-prints/plate_v3_v29_mirrorred.stl)                | 1            |
| [Right Case](https://github.com/Bastardkb/Charybdis/blob/2dad0ca/files/3x6%20mini/CMini_v1_v11.3mf)                              | 1            |
| [Left Case](https://github.com/erenatas/charybdis-wireless-3x6/blob/master/3d-prints/case_v3_v29_mirrorred.stl)                  | 1            |
| [Sensor Cover](https://github.com/Bastardkb/Charybdis/blob/9130a58/files/sensor_cover_v51.stl)                                   | 1            |
| [Adapter Top](https://github.com/Bastardkb/Charybdis/blob/c818c76/files/3x5%20nano/adapter_v2_top_v75.stl)                       | 1            |
| [Adapter Bottom](https://github.com/Bastardkb/Charybdis/blob/d0e20cc/files/mods/btu/adapter_btu_bottom_v32.stl)                  | 1            |
| [Ball Bearing Holder](https://github.com/Bastardkb/Charybdis/blob/322faad/files/mods/printable-btu/printable_btu_2.5mm_ball.stl) | 3            |

I ordered these parts from [JLC3DP](https://jlc3dp.com/3d-printing-quote) in SLS black 3201PA-F Nylon. After the order was reviewed I was warned that some of the parts were too thin and may bend or break during production. The risks were accepted and the parts arrived without issue.

The files for these are in the 3D Print STL Files directory, and the source repos have been linked in the parts list above.


### 3D Key Cap Prints

| **Part** | **Quantity** |
| -------- | ------------ |
| r1       | 2            |
| r2       | 2            |
| r3       | 2            |
| thumb    | 1            |

The key caps are DES profiled. These were designed by [pseudoku](https://github.com/pseudoku/PseudoMakeMeKeyCapProfiles), and the key set files in this repo will print sets of 10 keys for row one, two, and three, and a single set of ergo thumb keys.

JLC3DP SLS printed these in white 1172Pro Nylon. They sent the same warning asking for the risks to be accepted, and they all turned out fine as well.

Note - JLC3DP charges per-part, and only allows combining a maximum of 10 small parts into a single print, which is why the sprues are part of the STL files. However, if you have different printing requirements/capabilities, the OpenSCAD code from [toniz4](https://github.com/toniz4/PseudoMakeMeKeyCapProfiles) was forked and modified to allow rendering whatever keys you like, with or without sprues. If more than one set of keys is rendered at a time, and sprues are enabled, they will be meshed to make them a single part.

To render your own STL files, clone the [fork](https://github.com/280Zo/PseudoMakeMeKeyCapProfiles) and update the keeb.scad file as desired.

### PMW3610 Sensor

| **Part**                                                                                    | JLCPCB Part #                                                                | MFR. Part #       | **Quantity** |
| ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ----------------- | ------------ |
| [PMW3610 module with lens (LM18-LSI)](https://www.aliexpress.us/item/3256806022278018.html) | N/A                                                                          | N/A               | 1            |
| [LDO](https://www.mouser.com/ProductDetail/595-TLV70018DDCR)                                | [C79924](https://jlcpcb.com/partdetail/TexasInstruments-TLV70018DDCR/C79924) | TLV70018DDCR      | 1            |
| [Thick Film Resistor](https://www.mouser.com/ProductDetail/303-0603WAF2004T5E)              | [C22976](https://jlcpcb.com/partdetail/23703-0603WAF2004T5E/C22976)          | 0603WAF2004T5E    | 1            |
| [Ceramic Capacitors](https://www.mouser.com/ProductDetail/187-CL10A105KB8NNNC)              | [C15849](https://jlcpcb.com/partdetail/16531-CL10A105KB8NNNC/C15849)         | CL10A105KB8NNNC   | 1            |
| [Ceramic Capacitors](https://www.mouser.com/ProductDetail/603-CC603KRX7R9BB104)             | [C14663](https://jlcpcb.com/partdetail/Yageo-CC0603KRX7R9BB104/C14663)       | CC0603KRX7R9BB104 | 1            |
| [Ceramic Capacitors](https://www.mouser.com/ProductDetail/187-CL10A475KO8NNNC)              | [C19666](https://jlcpcb.com/parts/componentSearch?searchTxt=C19666)          | CL10A475KO8NNNC   | 7            |

These are all the components required for the sensor breakout PCB. It's possible to have JLCPCB assemble the PCB and components for you. Just select that option at checkout and supply the bom.csv and positions.csv from the PMW3610 Breakout zip.

I chose to solder the parts on myself so I ordered the parts above. A diagram of where to solder each component on is in the assembly instructions.

:information_source: [C79924](https://jlcpcb.com/partdetail/TexasInstruments-TLV70018DDCR/C79924)/TLV70018DDCR is a substitue for [C146366](https://jlcpcb.com/jp/partdetail/TOSHIBA-TCR2EF19_LMCT/C146366)/TCR2EF19,LM(CT) which is what the designer of the PCB originally used. Either component will work, but if you plan to have JLCPCB assemble the sensor board the C146366 is what's included in the parts list and is often out of stock. However, the replacement is normally available.

### General Components

| **Part**                                                                                                                                                             | **Quantity** |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| [Trackball](https://www.amazon.com/Perixx-18021-PERIPRO-303GR-Trackball-Compatible/dp/B071NX7Y2J)                                                                    | 1            |
| [SuperMini NRF52840 Microcontrollers](https://www.aliexpress.us/item/3256805848952479.html?gatewayAdapt=glo2usa)                                                     | 2            |
| [Mill Max Low Profile Sockets 315-43-112-41-003000 (optional)](https://www.mouser.com/ProductDetail/Mill-Max/315-43-112-41-003000?qs=s8Nb1z4Wn%2FRfWrVqQ0TOuQ%3D%3D) | 4            |
| [Mill Max Pins 3320-0-00-15-00-00-03-0 (optional)](https://www.mouser.com/ProductDetail/Mill-Max/3320-0-00-15-00-00-03-0?qs=s8Nb1z4Wn%2FQ16WBIwCPrTw%3D%3D)          | 48           |
| [1N4148W Signal Diodes](https://www.amazon.com/gp/product/B079KJX5J9/ref=ox_sc_act_title_1?smid=A14FP9XIRL6C1F&psc=1)                                                | 41           |
| [Button (4x4x1.5)](https://www.aliexpress.us/item/2255800859820067.html?gatewayAdapt=glo2usa4itemAdapt)                                                              | 2            |
| [Mini Toggle Switch SPDT 3mm](https://www.amazon.com/Position-Breadboard-Electronic-Miniature-SlideSwitch/dp/B09R42XQTB)                                             | 2            |
| [3.7V 130mAh 401030 Li-Po Batteries](https://www.aliexpress.us/item/3256805609268740.html?)                                                                          | 2            |
| [2.5mm Silicon Nitride Ceramic Ball Bearings](https://www.aliexpress.us/item/2255799954006155.html)                                                                  | 3            |
| [80MM Flexstrip Jumper Cables](https://www.aliexpress.us/item/3256803312420217.html)                                                                                 | 2            |
| [Gateron oil king 2.0 switch three-layer pin self-lubricating linear handle 55gf Key Switches](https://www.aliexpress.us/item/3256806388542736.html)                 | 41           |
| [M3 x D5 x L5 Brass Melt Nuts](https://www.aliexpress.us/item/3256805371193370.html)                                                                                 | 5            |
| [M4 x D6 x L5 Brass Melt Nuts](https://www.aliexpress.us/item/2255800046610840.html)                                                                                 | 12           |
| [M3 8mm Torx Screws](https://www.aliexpress.us/item/2251832820627860.html)                                                                                           | 5            |
| [M4 8mm Torx Screws](https://www.aliexpress.com/item/2251832820627860.html)                                                                                          | 12           |
| [JST plug 2-pin](https://www.aliexpress.com/item/2251832721663484.html)                                                                                              | 2            |
| [Adhesive bumper pads](https://www.amazon.com/Shintop-Furniture-Bumpers-Protection-Hemispherical/dp/B01DU0O00W)                                                      | 10           |

The parts above were ordered from Aliexpress and Amazon. If the links go to a listing that's no longer active, just search for something with the same description and specs.

The standard for microcontrollers on wireless keyboard builds is the nice!nano 2.0. However, there are some cheaper alternatives documented on [this MCU wiki](https://github.com/joric/nrfmicro/wiki/Alternatives). This build uses the SuperMini NRF52840.

You can order whatever battery you like, it just needs to be 3.7v and more than 80mAh. If you want it to fit under the micro controller, make sure the dimensions are correct. You'll also need to use the optional header sockets. You can order socket pins which are more sturdy than just using [diode legs](https://docs.splitkb.com/hc/en-us/articles/360011263059-How-do-I-socket-a-microcontroller#h_f7045b1e-5c02-4c73-8569-252b7fce7ad6).

## Assembly

Bastard Keyboard's build guides are excellent and comprehensive. Their material will be linked to as much as possible in the steps below.

**Tool List**
- soldering iron
- soldering iron fine tips
- lead free solder
- Solder wick and Desoldering Pump
- flux
- filter fan
- ESD mat and strap
- ESD safe tweezers
- Kapton tape
- Double sided tape
- torx screw drivers
- scissors
- Flush cutting pliers
- (optional) self closing tweezers or kelly forceps
- (optional) magnifying glass or microscope

**Melt nuts**

Follow BastardKB's [build guide to install screw inserts on the cases](https://docs.bastardkb.com/bg_charybdis/04screw_inserts.html).

Then follow thier [build guide to install screw inserts on the sensor assembly](https://docs.bastardkb.com/bg_charybdis/11sensor_assembly.html#preparing-the-3d-holder-assembly).

**Diodes**

BastardKB's documentation on how to [solder diodes on both plates and thumb clusters](https://docs.bastardkb.com/bg_charybdis/05diodes.html).

**Sensor Breakout Components (optional)**

If you've chosen to solder the components on the PMW3610 breakout PCB, follow the diagram below to get them in the correct spots.

A stand with a magnifying glass, or a digital microscope are very helpful in ensuring the soldering is done correctly on these small components.

![pmw3610_pcb](./images/PMW3610_component_diagram.png "Component Placement")

**PMW3610**

The lens of the sensor should be removed or covered with Kapton tape while soldering. Orient the sensor so that the back of it is on the same side as the other components, then solder it in place.

When working with the sensor and the MCU it's best to keep soldering iron temperatures below 300°C.

**Nano Holder Components**

Solder on the switches, and buttons to the left and right nano holder PCBs. Then solder on the JST female connectors. I positioned this so the red wire on the male side would be the battery's postive connection. I also had to bed the legs out a little bit in order to get this to fit flush with the nano holder board.

**MCU**

Solder the MCUs to the nano holders using the standard pin headers or the socketed pin headers, depending on what you chose to order to mount the MCU.

The MCUs should be face down (components pointed towards the PCB), and the top pins on either side of the USB connection will not have a connection to the PCB.

:warning: As mentioned above, do not set your soldering iron any higher than 300°C.

After the components have all been soldered, it should look something like the picture below.

![alt text](images/nano_holder.jpg)

Being careful to not short any connections, connect the JST battery connections, and confirm the MCU powers on.

**Cables**

If you want the cables a different color, make sure to paint them before this step. Use some tape to cover the tips so they can still be soldered.

Use [BastardKB's documentation](https://docs.bastardkb.com/bg_charybdis/07ribbon_cables.html#cutting-the-cables) on how to cut and solder the ribbon cables.

Then follow the [BastardKB docs](https://docs.bastardkb.com/bg_charybdis/09cables_to_splinky.html) on how to connect all of the PCBs together.

Make sure to use the flush cut pliers to remove any protruding pins and solder from the back side of the PCBs so that they can sit flush with the cases when the switches are being mounted.

For my build, I had some extra sockted pin headers laying around, so I chose to socket the sensor board to the MCU holder with some 28 gauge wire from an Ethernet cable. However, the ribbon cable would have worked just fine as well.

**Battery**

Most builds mount the battery under the MCU, however I opted to mount it on the top lip of each half with some double sided tape.

The fit is perfect and I haven't had any issues with it in this location.

![alt text](images/battery.jpg)

This allowed me to keep the battery away from components that could be damaged with excessive heat or expansion, and makes it easy to examine. The slack in the cable makes it simple to change or remove the battery at any time.

**Testing**

Now that everything is connected follow [BastardKB's documentation](https://docs.bastardkb.com/bg_charybdis/10install_the_switches.html#testing-the-pcbs) to test the switch pads and connections.

**Switches**

Once all the switch pads have been confirmed to work, install the switches by following [BastardKBs documentation](https://docs.bastardkb.com/bg_charybdis/10install_the_switches.html#installing-the-switches).

**Sensor PCB**

Put the sensor cover into the right case, install the BTU ball holders into the BTU bottom adatper, then screw the BTU bottom adatper into the sensor cover.

Make sure to push the BTU ball holders all the way into the BTU bottom adapter. They go in deeper than being flush with the side walls. It should something like this.

![alt text](images/btu_bottom.jpg)

Finally, install the sensor and sensor cover by screwing them into the BTU bottom adatper.

**Pads**

Install the anti-slip pads on to the bottom of each plate.

**Final Test**

Install the key caps, then connect each half to the computer the same way you did for the previous test. Confirm that each key still works.

# WIP

I'll be adding content for some additional steps soon:
- How to dye the keys
- How to configure the firmware
- How to flash the firmware
- Key layouts

# Credits
This was my first keyboard build, and I couldn't have done it without the hard work from many others:
- [BastardKB](http://bastardkb.com/)
- [erenatas](https://github.com/erenatas/charybdis-wireless-3x6/blob/master/README.md)
- [pseudoku](https://github.com/pseudoku/PseudoMakeMeKeyCapProfiles)
- [toniz4](https://github.com/toniz4/PseudoMakeMeKeyCapProfiles)
- [VOID](https://github.com/victorlucachi)
- [olidacombe](https://github.com/olidacombe)
- [EIGA](https://www.youtube.com/watch?v=Mks7QDxFreY)
