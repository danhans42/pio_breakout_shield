# pio_breakout_shield

Simple shield for a 39SF020, CH375/6 and Atmel ATF22V10 - for use on a Sony PlayStation console for expansion experimentation. Pretty much the basis for a modern replacement PIO cart,

![image](https://github.com/danhans42/pio_breakout_shield/blob/main/images/pio_breakout_ch376.jpg)

Requires the PIO-Breakout (https://github.com/grumpycoders/pcsx-redux/wiki/PIO-Breakout), part of the PCSX-Redux project - https://pcsx-redux.consoledev.net/ which this board is designed to plug onto.

The board that be populated as much or as little as required. It can provide a simple 256k boot ROM so the PlayStation can boot from it - handy for Unirom etc. Alternatively you can add/program the SPLD (ATF22v10C), add a CH375/6 to it and you have a bootable cartridge that allows for USB host/device experimentation. 

The ATF22v10c can be programmed with a TL866 programmer, as can the EEPROM. If you wish to play around with the configuration you will need to obtain WinCUPL (https://www.microchip.com/en-us/products/fpgas-and-plds/spld-cplds/pld-design-resources) to build the equations. Unfortunately I do not know of a modern, open-source equivalent to work with these parts.

Alternatively if you happy to go with it as is, you can just burn the provided jed which will give you the default configuration. (todo - document layout)

To note: the PCB layout and design is the work of Nicolas Noble who was kind enough to design this for me. Thanks for this and the PIO-Breakout, without none of this would have been possible.

The PIO connectors can be difficult to source. See the information in the pcsx-redux wiki on the subject here, https://github.com/grumpycoders/pcsx-redux/wiki/PIO-port-replacement. Digikey link https://www.digikey.co.uk/en/products/detail/molex/0015921468/480913. They are also available on AliExpress for around $1.80 (link to follow). They do however require modification with a dremel slightly.

For more info or psx related chat - join us on psx.dev discord (http://psx.dev/)

