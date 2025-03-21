# ModXo-RP2040-Tiny

![alt text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/logo.png?raw=true) <img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/team-resurgent.png" width="180"> <img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/Nemesis.png" width=180> ![alt text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/DC%20logo.png?raw=true)

<a href="https://discord.gg/k2BQhSJ"><img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/discord.svg"></a>

A carrier board for the ModXo V1.0 with added support for Epimetheus

This is designed around Team Resutgent's and Shalx's work on ModXo an open-source modchip, with additional support for OfficialTeamUIX's Epimetheus incorporated into the PCB

<img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/Board.jpg" width=350>

Mouser Cart: <a href="https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=a62729557a">Here</a>

RP2040 Tiny: <a href="https://www.aliexpress.us/item/3256805837992528.html?spm=a2g0o.productlist.main.21.2f7926c5zGZBOW&algo_pvid=a59806cb-1f8b-4000-8595-0b05ca9fd6e6&algo_exp_id=a59806cb-1f8b-4000-8595-0b05ca9fd6e6-10&pdp_npi=4%40dis%21USD%217.22%214.48%21%21%217.22%214.48%21%402101c80217323295821625728e786b%2112000035369681956%21sea%21US%21196794698%21X&curPageLogUid=5ESoEvR4Kxce&utparam-url=scene%3Asearch%7Cquery_from%3A">AliExpress</a>, <a href="https://www.amazon.com/gp/product/B0CHDW1MY5/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1">Amazon</a>

JST SH 6 Pin Cables: 

<a href="https://www.aliexpress.us/item/3256804332710255.html?spm=a2g0o.detail.pcDetailTopMoreOtherSeller.5.245bNc4KNc4Kdm&gps-id=pcDetailTopMoreOtherSeller&scm=1007.40050.354490.0&scm_id=1007.40050.354490.0&scm-url=1007.40050.354490.0&pvid=6b58b5af-718a-4929-bfb1-9a0c24fd9d3c&_t=gps-id:pcDetailTopMoreOtherSeller,scm-url:1007.40050.354490.0,pvid:6b58b5af-718a-4929-bfb1-9a0c24fd9d3c,tpp_buckets:668%232846%238112%231997&pdp_npi=4%40dis%21USD%210.46%210.40%21%21%210.46%210.40%21%402103241117302619299196939e5dfc%2112000029449896682%21rec%21US%21196794698%21X&utparam-url=scene%3ApcDetailTopMoreOtherSeller%7Cquery_from%3A">AliExpress</a> Select 100mm length, 6 Pin 10 Pcs, SH 1.0MM Dual for Color, Request same direction!!!

Or if you want to build out your own you can use this listing on <a href="https://www.amazon.com/gp/product/B0BKSNMCV4/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1">Amazon</a>






For more information on the software side of things and the ModXo project please visit: https://github.com/Team-Resurgent/Modxo

For more information on Epimetheus please visit: https://github.com/OfficialTeamUIX/Epimetheus 

### Notice

No firmware is provided for the STM32 you will need to either code your own firmware or legally obtain a firmware image

#### Builder's note

If your XBOX is a revision 1.6 you will need to rebuild the LPC manually or use a LPC rebuild PCB.



# Purchase

Fully assembled boards and PCB's can be purchased via <a href="https://darkonecustoms.com">Darkone Customs</a>

PCB Only: <a href="https://www.darkonecustoms.com/store/p/modxo-epimetheus-pcb">Here</a>

Fully Assembled Board: <a href="https://www.darkonecustoms.com/store/p/modxo-epimetheus-fully-assembled">Here</a> *Fully assembled boards do not contain any firmware for the STM32*


# Navigation

Both the Bom and iBOMS are located in the root folder. iBOMS are included for the full-size board and the new Smol revision, Large board has been moved to archive

Archive: Will contain older functional gerbers and pick and place files as the board revs, along with older board images and older iBOMS.

Images: Contains branding images along with PCB images for the full-size and the Smol board, the schematic is also included here and is the same for both boards along with images of the various header pinouts and soldering locations

Smol: Contains gerbers for the Smol board along with the pick-and-place file






# Assembly

### ModXo

It's recommended to assemble the ModXo potion of the board first and test it. These parts include U1, D1, LED2, R1-4, R6, and the LPC headder. After functionality has been confirmed move on to the VCC circuit assembly

### VCC circuit

The VCC Circuit pulls 5V and GND from the LPC 5V on the 5V pad and GND can be found on PINs 2,12. The VCC circuit consists of the following parts U5, L1, C1-C2. After assembly, you can test PIN 5 of U5 to ensure a stable 3.3V output. Once you have confirmed you have 3.3V continue to assemble the STM32 circuit

### STM32

The STM32F030C8C6 is the core of the Epimetheus functionality portion of the board these components include U2. R7-10, C3-C6. Do not install R9 until you have programmed your STM32. Once assembly is complete you can proceed to program your STM32 Review the NRST Harness diagram and temporarily install it for programming. The NRST wire will connect to the top pad of R9 (the one closest to the MCU) and the GND side to any viable GND source. Remove the NRST harness once you have verified and tested your firmware. Install R9 to complete the STM32 circuit. SDA is pulled directly from PIN 13 of the LPC header and SCL is pulled directly from PIN 14. Pinouts will be listed below. Proceed to Port assembly

#### STM32 PWR and Enable
Attach a +5V source to the 5V pad on the topside of the board. On the back of the board jumper, both boxes are labeled enable with a solder blob. This was designed this way to assist in isolating the STM32 and the ModXo. As a quick tap, you can pull +5V from the bottom of LED2. 

<img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/5V_TAP.png" width="275"> <img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/SM_EN.png" width="275">

### Port Assembly

Install U3, DISP, i2c_EXP, RGB_EXP, if using the RGB_EXP port install the jumper wire from the tiny to the RGB TP to enable the functionality.

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/RGB_EN.png?raw=true)

### Notice

Soldering in the header for PROG is optional as you can insert pins and lightly wedge them in place to program the chip, R5, R6, LED1, and LED2 are optional. LED2 needs to be installed reverse of what the silk screen has labeled


# Installation

## 1.0 - 1.4

Install your pin header, Run a short wire from any suitable D0 point to either ground or the D0 point on the ModXo-Basic. Plug-in your ModXo-Basic to the XBOX LPC port (after you have flashed your favorite firmware) and enjoy.

#### D0 Point options

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/d0.png?raw=true)

## 1.6

Either install a LPC rebuild QSB or rebuild your LPC per the rebuild diagram below. Plug-in your ModXo-Basic to the XBOX LPC port (after you have flashed your favorite firmware) and enjoy.

#### 1.6 LPC rebuild

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/16rebuild.png?raw=true)

# Pinouts 

Xbox LPC

![atl_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/LPC.png?raw=true)

Prog: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/PROG.png?raw=true)

U3: 

<img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/U3.png" width="375">

RGB_EXP: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/RGB_EXP.png?raw=true)

i2c_EXP: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/i2c_EXP.png?raw=true)

DISP: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/DISP.png?raw=true)

NRST Harnes:

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/NRST.png?raw=true)
