### 2023-02-09 MARLIN 2.1.2 RELEASE

📝**IMPORTANT NOTE**: 
Most of the problems with the SR come from the detrimental interaction of the Stock display (serial exchanges on the USB port, UART) on the operation of the old Marlin modified by FLSun. This leads to problems with step loss/skipping with the stepper motor drivers, extruder noise, blocking in some prints, ... (TMC in UART mode) or problems of dialogue priority with Octoprint, Repetier server or pronterface (USB) and the TFT screen.

- [ ] **So all my firmwares work without this weak link but with another TFT screen and contain all the last improvements of Marlin.**  

♻️ **Caution for SR printer**♻️: 
The SR printer has two types of motherboards (MoBo). The first ones have BTT_SKR13 and the new ones have Mks_robin_nanoV3.x. 
These are not the same firmwares for Marlin so be careful when downloading to take the right firmware associated with the MoBo.

SKR13 => Firmware SRB_xxxxxxx.bin

Nano3.x => Firmware SRM_xxxxxxxx.bin

Each firmware has a header that corresponds to the hardware (board) and functions used in the firmware.

**ADD:**
- Pack Firmware for BTT-TFT35/50/70 mode landscape and portrait for TFT35v3. 
- BTT-TFT35v3 (**Option "r"**), 

  ⚡️Compatible with all SR motherboards(MoBo) and for users who print only via media (SD card, USB sticks)
  
  <img width=400 src="https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/menus/SR-TFT35v3.png" />

- Mks-TS35R (**Option "C"**),
 
  ⚡️Compatible only with the NanoV3.x MoBo with EXP1/EXP2 connectors (some users have received a MoBo without these connectors) and for all users who print via media (SD card, USB sticks) or from hosts (Octoprint, Repetier server, Pronterface, etc) 
  
  <img width=700 src="https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/menus/SR-TS35R.png" />


Below is an example with the firmware for a SR printer (STOCK) with a Mks_Robin_nanoV3 board with 4xTMC2209 drivers and another TFT screen (Mks-TS35R):

**Exemple:**
SRM-SCBPULR32-Robin_nano_v3.bin
=> SRM = SR with MKS Nano_V3 board.
   SRB = SR with BTT Skr_v1.3 board.
  - (S)4xTMC2209 in UART mode - Stock
  - (C)UI Color Marlin RepRap TFT - (Mks-TS35R)  
  - (B)Extruder BMG
  - (P)PreHeat bed (60°C) 
  - (U)Leveling mode UBL
  - (L)LinearAdvance enabled
  - (R)Arc function enabled
  - (32) All axes in 32 steps instead of 16 steps.

  🔧**Note**: After choosing your binary, remove the "SRM-SCBPULR32-" header or rename the file to "Robin_nano_v3.bin" for SR-MKS,
  place it on your SD card, insert your SD card into the printer and power on your printer.
  
  After the flash and to configure and prepare your printer, please follow the steps on the Wiki
  
  => [<img width=400 src="https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/icons/FLSun-Wiki.png" />](https://github.com/Foxies-CSTL/Marlin_2.1.x/wiki/2.SETTINGS-THE-PRINTER)

  or for a summary of [the steps to follow](../Instructions.md)

  📌**New 2023:**
  *Due to the increasing number of user requests and combinations of different HotEnd, MoBo and software features, I can build a firmware suitable for your configuration: A small contribution will be asked* 🍻.
  
  **Header caption:**

  **/*------Drivers--------*/**
  - (S) Stock=4xTMC2209_UART. (default)
  - (32) All drivers 32steps (TMC-UART)

  **/*-------Options UI TFT--------*/**
  - (F) UI STANDARD (Emulation LCD screen on TFT)
  - (C) UI MARLIN (TFT Color screen like Mks TS35v2) (default)
  - (I) UI MKS (TFT Color screen>=480x320 use Lvgl/NANOv3)
  - (r) UI STANDARD (TFT Color screen like BTT-TFT35v3 or Marlin Mode Emulation)
  - (D) UI DWIN (TFT DGUS Color screen like Mks H43)

  **/*------Modules--------*/**
  - (N) NeoPixel (management of led strips, +number = nb leds)
  - (W) Module ESP8266/ESP12 (infos at the middle of the page)
  - (w) Module ESP8266/ESP12 with ESP3Dv3.0 Firmware.
  - (B) Extruder BMG right_hand (Stock) (default)
  - (O) Extruder OMG v2
  - (X) Extruder DirectDrive NEMA14 Pancake (**SDHX**/Mini-Sherpa/Orbiter/Salfin)
  
  **/*-------Others options in firmware----*/**
  - (G) SENSORLESS_HOMING (Only 2209)
  - (g) SENSORLESS_PROBING (Only 2209)
  - (m) MPCTEMP - Model predictive temperature control (New PID)
  - (H) Hotend Volcano or HotendAllMetal (+number = type thermistor)
  - (U) BED_LEVELING_UBL (default)
  - (P) PreHeat bed before leveling (default)
  - (R) ARC_SUPPORT (default)
  - (L) Linear Advance (default)
  - (M) MEATPACK (Improve dialogue/communication with OctoPrint) (default)
  - (Z) Input Shaping. (No validated on Deltas)
  
  **/*-------Others options for advanced users who build their firmware----*/**
  - HOST_ACTION_COMMANDS (Action Command Prompt support Message on OctoPrint) (default)
  - Host start print by menu (Only TFT_COLOR_UI)
  - BINARY_FILE_TRANSFER
  - TEMP_SENSOR_0 (After changed the thermitor nozzle)
  - LCD_LANGUAGE (Change to the native language)
  - FW retract (Default)
  - Add line for nb of leds.
  - Fixed "Special Menu" for MPC and levelings.
  - etc 
  
***
 ## ✨Support my work✨

  This FLSun Deltas porting project for Marlin firmware was only possible thanks to its supporters, you can participate:
 <br/>
  <br/> Via [![paypal.me](./icons/paypal_50px.png)](https://www.paypal.me/Foxies40)<br/>[![Donate](https://img.shields.io/badge/Donate-Thanks-green)](https://paypal.me/Foxies40)<br/>
<br/>
 
Via   <a href='https://ko-fi.com/U7U77F782' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://cdn.ko-fi.com/cdn/kofi4.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>   with a Mini-Blog.

  You can also send me a tip via [Thingiverse](https://www.thingiverse.com/FamStel/about) if you prefer.
 ### Massive thank you in advance :heart:
***
