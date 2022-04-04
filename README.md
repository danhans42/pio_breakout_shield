# pio_breakout_shield

Simple shield for a 39SF020, CH375/6 and Atmel ATF22V10 - for use on a Sony PlayStation console for expansion experimentation

Requires the PIO-Breakout (https://github.com/grumpycoders/pcsx-redux/wiki/PIO-Breakout) which is part of the PCSX-Redux project - https://pcsx-redux.consoledev.net/ which this board is designed to plug onto.

It is a simple board that can be populated as much or as little as you need. It can provide a simple 256k boot rom so the PlayStation can boot from it, handy for Unirom etc. Alternatively you can add/program the SPLD (ATF22v10C), add a CH375/6 to it and you have a bootable cartridge that allows for USB host/device experimentation. 

The SPLD can be programmed with a TL866 programmer, as can the EEPROM. If you wish to play around with the configuration you will need to obtain WinCUPL (https://www.microchip.com/en-us/products/fpgas-and-plds/spld-cplds/pld-design-resources) to build the equations. Alternatively if you happy to go with it as is, you can just burn the provided jed which will give you the default configuration.



To note: the PCB layout and design is the work of nicolasnoble who was kind enough to design this for me.
