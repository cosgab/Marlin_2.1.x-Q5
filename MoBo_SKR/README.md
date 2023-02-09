### 2023-02-09 MARLIN 2.1.x

Each firmware has a header that corresponds to the hardware (board) and functions used in the firmware.

**ADD:**
  - Pack Firmware for BTT-TFT35/70 mode landscape and portrait for TFT35v3. 

Below is an example with the firmware for a QQS printer with a MKS-NanoV3 board with 4xTMC2209 stepper drivers and BMG_right extruder:

**Exemple:**
QQSP+BTT-U9rBPULR32-SKR2b-firmware.bin
=> 
  - (U9)4xTMC2209 UART - 
  - (r)UI Classic/Touch with BTT-TFT35v3 - 
  - (B)Extruder BMG Right_ hand - 
  - (P)PreHeat bed - 
  - (U)Leveling mode -
  - (L)LinearAdvance - 
  - (R)Arc function enabled -
  - (32)Steps nb -
  - (MoBo) SKR2 revision b

  🔧**Note**: After choosing your binary, remove the "8CWBL-SRKxx" header or rename the file to "firmware.bin" for QQS-SKR,
  place it on your SD card, insert your SD card into the printer and power on your printer.
  
  After the flash and to configure and prepare your printer, please follow the steps on the Wiki => [🚸](https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/2.SETTINGS-THE-PRINTER)
  
<img width=400 src="https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/icons/FLSun-Wiki.png" />

  or for a summary of [the steps to follow](../Instructions.md)

  📌**New 2023:**
  *Due to the increasing number of user requests and combinations of different HotEnd, MoBo and software features, I can build a firmware suitable for your configuration: A small contribution will be asked* 🍻.
  
  **Header caption:**
  
  - P = Probe (Purple)
  - R = Runout for the filament (Orange)
  - F = Fan1 for the HeatSink (Green) (begin at 50°C)

  ![Cnx_SKR13](https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/images/SKR13_EndStop.png)
  ![Cnx_SKR14](https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/images/SKR14_EndStop.png)
  ![Cnx_SKR2](https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/images/SKR2_EndStop.png)

  **/*-------Others Firmwares for QQS with SKR family or Mks_Nano Family----*/**
  - (QQS)U9rTPULR16-SKR14T_firmware   QQS SKR14T(4xTMC2209UART)16steps with TITAN extruder. 
  - (QQS)U8rBPUR32-SKR13_firmware  QQS SKR13(4xTMC2208_standAlone)32steps without LA, with BMG Right_Hand extruder.
  - (QQS)U9rTPULR16-SKR14_firmware QQS with SKRv1.4 Board with emulation LCD (Marlin Mode)

  **/*------Drivers--------*/**
  - (S) A4988 (green/red)
  - (8) TMC2208 Standalone
  - (9) TMC2209 Standalone
  - (U8) 4xTMC2208_UART with no module ESP12.
  - (U9) 4xTMC2209_UART with no module ESP12.
  - (U8+) 3xTMC2208 (XYZ) + Choice for E0 (A4988,TMC220x) 
  - (U9+) 3xTMC2209 (XYZ) + Choice for E0 (A4988,TMC220x)
  - **(UH) 4xTMC2209_UART with one wire (option modules Wifi/Rpi/Neopixel)**
  - (16) All drivers 16steps (Default)  
  - (32) All drivers 32steps (TMC-UART)

  **/*-------Options UI TFT--------*/**
  - (F) UI STANDARD (Emulation LCD screen on TFT)
  - (C) UI MARLIN (TFT Color screen with TS35v2)
  - (I) UI MKS (TFT Color screen>=480x320 use Lvgl/NANOv2-3)
  - (r) UI STANDARD (For BTT-TFT screen with Marlin Mode Emulation on TFT )

  **/*------Modules--------*/**
  - (n) NeoPixel (management of led strips)
  - (W) Module ESP8266/ESP12 (infos at the middle of the page)
  - (w) Module ESP8266/ESP12 with ESP3Dv3.0 Firmware.
  - (T) Extruder Titan(Stock)/BMG left_Hand
  - (B) Extruder BMG Right_Hand (Also reverse the extruder direction)
  - (X) Extruder Nema14 (SuperDriveHX/Mini-Sherpa/Orbiter...)
  
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
  - BINARY_FILE_TRANSFER (default)
  - TEMP_SENSOR_0 (After changed the thermitor nozzle)
  - LCD_LANGUAGE (Change to the native language)
  - Add line for nb of leds.
  - Fixed "Special Menu" for MPC and levelings.
  - etc 
 ## ✨Support my work✨

  This FLSun Deltas porting project for Marlin firmware was only possible thanks to its supporters, you can participate:
 <br/>
  <br/> Via [![paypal.me](./icons/paypal_50px.png)](https://www.paypal.me/Foxies40)<br/>[![Donate](https://img.shields.io/badge/Donate-Thanks-green)](https://paypal.me/Foxies40)<br/>
<br/>
 
Via   <a href='https://ko-fi.com/U7U77F782' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://cdn.ko-fi.com/cdn/kofi4.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>   with a Mini-Blog.

  You can also send me a tip via [Thingiverse](https://www.thingiverse.com/FamStel/about) if you prefer.
 ### Massive thank you in advance :heart:
***
