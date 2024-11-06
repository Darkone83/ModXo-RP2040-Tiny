# ModXo-RP2040-Tiny

![alt text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/logo.png?raw=true) <img src="https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/team-resurgent.png" width="180"> ![alt text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/DC%20logo.png?raw=true)

A carrier board on the ModXo V1.0 with added support for Epimetheus

This is designed around Team Resutgents and Shalx's work on ModXo an open-source modchip, with additional support for OfficialTeamUIX's Epimetheus incorporated into the PCB

Mouser Cart: <a href="https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=a62729557a">Here</a>

RP2040 Tiny: <a href="https://www.aliexpress.us/item/3256805774173283.html?spm=a2g0o.productlist.main.1.768926c5xGqf43&algo_pvid=bcab3737-b299-4011-bb81-f2fe84c1f134&algo_exp_id=bcab3737-b299-4011-bb81-f2fe84c1f134-0&pdp_npi=4%40dis%21USD%212.57%212.57%21%21%212.57%212.57%21%402103247917302589896552613e3336%2112000035053449108%21sea%21US%21196794698%21X&curPageLogUid=SP1s83SK4sOp&utparam-url=scene%3Asearch%7Cquery_from%3A">AliExpress</a>, <a href="https://www.amazon.com/gp/product/B0CHDW1MY5/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1">Amazon</a>

JST SH 6 Pin Cables: 

<a href="https://www.aliexpress.us/item/3256804332710255.html?spm=a2g0o.detail.pcDetailTopMoreOtherSeller.5.245bNc4KNc4Kdm&gps-id=pcDetailTopMoreOtherSeller&scm=1007.40050.354490.0&scm_id=1007.40050.354490.0&scm-url=1007.40050.354490.0&pvid=6b58b5af-718a-4929-bfb1-9a0c24fd9d3c&_t=gps-id:pcDetailTopMoreOtherSeller,scm-url:1007.40050.354490.0,pvid:6b58b5af-718a-4929-bfb1-9a0c24fd9d3c,tpp_buckets:668%232846%238112%231997&pdp_npi=4%40dis%21USD%210.46%210.40%21%21%210.46%210.40%21%402103241117302619299196939e5dfc%2112000029449896682%21rec%21US%21196794698%21X&utparam-url=scene%3ApcDetailTopMoreOtherSeller%7Cquery_from%3A">AliExpress</a> Select 100mm length, 6 Pin 10 Pcs, SH 1.0MM Dual for Color, Request same direction!!!

Or if you want to build out your own you can use this listing on <a href="https://www.amazon.com/gp/product/B0BKSNMCV4/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1">Amazon</a>





For a smaller build, there is an iBOM (Smol) in the root folder and gerbers in the Smol directory

For more information on the software side of things and the ModXo project please visit: https://github.com/Team-Resurgent/Modxo

For more information on Epimetheus please visit: https://github.com/OfficialTeamUIX/Epimetheus 

### Notice

No firmware is provided for the STM32 you will need to either code your own firmware or legally obtain a firmware image






# Navigation

Both the Bom and iBOMS are located in the root folder. iBOMS are included for the full-size board and the new Smol revision

Images: Contains branding images along with PCB images for the full-size and the Smol board, the schematic is also included here and is the same for both boards along with images of the various header pinouts and soldering locations

PCB: Contains the gerbers for the full-size board along with the pick-and-place file

Smol: Contains gerbers for the Smol board along with the pick-and-place file






# Assembly

### ModXo

It's recommended to assemble the ModXo potion of the board first and test it. These parts include U1, D1, LED2, R1-4, R6, and the LCP headder. After functionality has been confirmed move on to the VCC circuit assembly

### VCC circuit

The VCC Circuit pulls 5V and GND from the LPC 5V on PIN 6 and GND can be found on PINs 2,12. The VCC circuit consists of the following parts U5, L1, C1-C2. After assembly, you can test PIN 5 of U5 to ensure a stable 3.3V output. Once you have confirmed you have 3.3V continue to assemble the STM32 circuit

### STM32

The STM32F030C8C6 is the core of the Epimetheus functionality portion of the board these components include U2. R7-10, C3-C6. Once assembly is complete you can proceed to program your STM32. SDA is pulled directly from PIN 13 of the LPC header and SLC is pulled directly from PIN 14. Pinouts will be listed below. Proceed to Port assembly

### Port Assembly

Install U3, DISP, i2c_EXP, RGB_EXP, if using the RGB_EXP port install jumper wire from the tiny to the RGB TP to enable the functionality

### Notice

Soldering in the header for PROG is optional as you can insert pins and lighty wedge them in place to program the chip




# Pinouts 

Xbox LPC

![atl_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/LPC.png?raw=true)

Prog: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/PROG.png?raw=true)

U3: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/U3.png?raw=true)

RGB_EXP: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/RGB_EXP.png?raw=true)

i2c_EXP: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/i2c_EXP.png?raw=true)

DISP: 

![alt_text](https://github.com/Darkone83/ModXo-RP2040-Tiny/blob/main/Images/DISP.png?raw=true)


