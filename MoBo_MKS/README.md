### 2023-02-09 MARLIN 2.1.x

- QQS-Pro With MoBo Nanov3+4xTMC2209 = QQSP_TFT-header-Robin_nano_v3.bin
- QQS-Pro With MoBo SRK+4xTMC2209 = QQSP_STOCK-header-MoBo-firmware.bin
- QQS-Pro STOCK With 4xTMC2209 = QQSP_STOCK_TMC9-Robin_mini.bin
  
Each firmware has a header that corresponds to the hardware (board) and functions used in the firmware.

New 2023:
Due to the increasing number of user requests and combinations of different HotEnd, MoBo and software features, I can build a firmware suitable for your configuration: A small contribution will be asked.

**ADD:**
 - Pack Firmware for BTT-TFT35/70 mode landscape and portrait for TFT35v3. 

Below is an example with the firmware for a QQS printer with a MKS-NanoV3 board with 4xTMC2209 stepper drivers and BMG_right extruder:

**Exemple:**
QQSP+TS35-U9CBPULR32-Robin_nano_v3.bin
=> 
 - (U9)4xTMC2209 UART - 
 - (C)UI Marlin with TFT TS35v2 - 
 - (B)Extruder BMG Right_ hand - 
 - (P)PreHeat bed - 
 - (U)Leveling mode -
 - (L)LinearAdvance - 
 - (R)Arc function enabled -
 - (32)Steps nb -
 - (MoBo) NanoV3

  🔧**Note**: After choosing your binary, remove the "QQSP_TS35-U9CBPULR32-" header or rename the file to "Robin_nano_v3.bin" for QQS or "firmware.bin".
  place it on your SD card, insert your SD card into the printer and power on your printer.
  
  After the flash and to configure and prepare your printer, please follow the steps on the Wiki => [🚸](https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/2.SETTINGS-THE-PRINTER)
  
<img width=400 src="https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/icons/FLSun-Wiki.png" />

  or for a summary of [the steps to follow](../Instructions.md)

  📌**New 2023:**
  *Due to the increasing number of user requests and combinations of different HotEnd, MoBo and software features, I can build a firmware suitable for your configuration: A small contribution will be asked* 🍻.


**Header caption:**
 - P = Probe (Purple)
 - R = Runout for the filament (Orange)
 - F = Fan1 for the HeatSink (Green) (begin at 80°C)

![Cnx_NanoV3](https://github.com/Foxies-CSTL/Marlin_2.0.x/wiki/images/NanoV3-EndStop.png)

  **/*------Drivers--------*/**
  - (S) A4988 (green/red rectangle)
  - (8) TMC2208 Standalone
  - (9) TMC2209 Standalone
  - (U8) 4xTMC2208_UART with no module ESP12.
  - (U9) 4xTMC2209_UART with no module ESP12.
  - (U8+) 3xTMC2208 (XYZ) + Choice for E0 (A4988,TMC220x) 
  - (U9+) 3xTMC2209 (XYZ) + Choice for E0 (A4988,TMC220x)
  - (16) All drivers 16steps (Default)
  - (32) All drivers 32steps (TMC-UART)

  **/*-------Options UI TFT--------*/**
  - (F) UI STANDARD (Emulation LCD screen on TFT)
  - (C) UI MARLIN (TFT Color screen)
  - (I) UI MKS (TFT Color screen>=480x320 use Lvgl/NANOv2-3)
  - (r) UI STANDARD (Marlin Mode on BTT-TFT FOR SKR/NANOv2-3)
  - (D) UI DWIN (H43)

  **/*------Modules--------*/**
  - (n) NeoPixel (management of led strips)
  - (W) Module ESP8266/ESP12 (infos at the middle of the page)
  - (w) Module ESP8266/ESP12 with ESP3Dv3.0 Firmware.
  - (T) Extruder Titan/Stock
  - (B) Extruder BMG
  - (X) Extruder Nema14 (SuperDriveHX/Mini-Sherpa/Orbiter/...)
  
  **/*-------Others options in firmware----*/**
  - (G) SENSORLESS_HOMING (Only 2209)
  - (g) SENSORLESS_PROBING (Only 2209)
  - (m) MPCTEMP - Model predictive temperature control
  - (H) Hotend Volcano or HotendAllMetal
  - (A) BED_LEVELING_BILINEAR
  - (U) BED_LEVELING_UBL
  - (P) PreHeat bed before leveling
  - (R) ARC_SUPPORT
  - (L) Linear Advance (Possible Bug with BabyStep and TMC2208)
  - (M) MEATPACK (Improve dialogue/communication with OctoPrint)

  **/*-------Others options for advanced users who build their firmware----*/**
  - HOST_ACTION_COMMANDS (Action Command Prompt support Message on OctoPrint) (default)
  - Host start print by menu (Only TFT_COLOR_UI)
  - BINARY_FILE_TRANSFER (default)
  - TEMP_SENSOR_0 (After changed the thermitor nozzle)
  - LCD_LANGUAGE (Change to the native language)
  - Add line for nb of leds.
  - Fixed "Special Menu" for MPC and levelings.
  - etc 
   
  **/*-------Others Firmwares for Q5 nanov1.2 or QQS with SKR family or Mks_Nano Family----*/**
  - (Q5_8+SCTPULR-Robin_nano)   Q5 Stock(3xTMC2208+1xA4988) with TITAN extruder. 
  - (Q5_9CBPULR-Robin_nano)     Q5 with 4xTMC2209 with BMG extruder.
  - (QQS)U9rTPULR16-SKR14_firmware QQS with SKRv1.4 Board with emulation LCD (Marlin Mode)
 ## ✨Support my work✨

  This FLSun Deltas porting project for Marlin firmware was only possible thanks to its supporters, you can participate:
 <br/>
  <br/> Via [![paypal.me](./icons/paypal_50px.png)](https://www.paypal.me/Foxies40)<br/>[![Donate](https://img.shields.io/badge/Donate-Thanks-green)](https://paypal.me/Foxies40)<br/>
<br/>
 
Via   <a href='https://ko-fi.com/U7U77F782' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://cdn.ko-fi.com/cdn/kofi4.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>   with a Mini-Blog.

  You can also send me a tip via [Thingiverse](https://www.thingiverse.com/FamStel/about) if you prefer.
 ### Massive thank you in advance :heart:
***
