# pio_breakout_shield

Simple shield for a 39SF020, CH375/6 and Atmel ATF22V10 - for use on a Sony PlayStation console for expansion experimentation. Pretty much the basis for a modern replacement PIO cart. The parts used are(were?) easily obtainable from your online marketplace of choice.

PCB's
=====

PCB's - I used JLCPCB for production and found them very well priced, with quick delivery to me (UK). Quality was also very good, Files are provided here for the shield itself, the breakout PCB files are available on the pcsx repo - see further down this document.

Example configuration - 'fully loaded'

![image](https://github.com/danhans42/pio_breakout_shield/blob/main/images/pio_breakout_ch376.jpg)

Parts List
==========

- SST39SF020 EEPROM (2Megabit)
- WCH 375/376 module (Either works - 376 is better as it has FAT/FAT32 support)
- Atmel ATF22V10C SPLD (GAL/PAL like device)
- 7805 type 5v regulator (i used a little module for efficiency)
- few caps for decoupling
- DIP32 socket
- PCB Pins - enough to join the bords together or use your own solution
- 68 way expansion connector (see later on for details)

When fitting the CH Module - you will notice that the connector is not correctly placed to allow for correct connection, the connect must be removed from the module and soldered from the beneath. See the image above.

PIO Breakout
============

PIO-Breakout is a seperate PCB (https://github.com/grumpycoders/pcsx-redux/wiki/PIO-Breakout), part of the PCSX-Redux project - https://pcsx-redux.consoledev.net/ which this board is designed to plug onto. You can find the files for the pcb in the repository.

The breakout board is great for expansion experimentation and highly recomended.

PIO Connector
=============

The PIO connectors can be difficult to source. See the information in the pcsx-redux wiki on the subject here, https://github.com/grumpycoders/pcsx-redux/wiki/PIO-port-replacement. Digikey link https://www.digikey.co.uk/en/products/detail/molex/0015921468/480913. They are also available on AliExpress for around $1.80 (link to follow). They do however require modification with a dremel slightly.

Alternatively if you are desperate you can source one from a faulty HK AR clone or such,

pio_breakout_shield Configuration
=================================

The board that be populated as much or as little as required. It can provide a simple 256k boot ROM so the PlayStation can boot from it - handy for Unirom etc. Alternatively you can add/program the SPLD (ATF22v10C), add a CH375/6 to it and you have a bootable cartridge that allows for USB host/device experimentation. 

The provided config (PSX_PLORER in \atf22v10c folder) for the SPLD provides the following :- 

- 256k flash @ 0x1f000000 in one block (like xplorer)
- CH37x @ 0x1f060002 (data)/0x1f060003 (cmd)
- rom enable jumper (bridge) IO15/IO14 (useful if you screw up the rom and want to recover without cart hotswapping)

This is very basic, its my intention to add some form of GPIO via the remaining pins but I currently do not have the patience with WinCUPL.
If you so chose, you could fit a 29EE020 and be able to use the standard xplorer firmware (non pro/fx) with this config.

The CH-375 supports usb device(CH372) and host mode for mass storage. However the CH376 in addition has built in FAT16/32 file system support. In future I will upload some source examples for host most such as USB Mouse examples etc. and for mass storage. 

ATF22V10C Programming
=====================

The ATF22v10c can be programmed with a TL866 programmer, as can the EEPROM itself. If you wish to play around with the configuration of the SPLD you will need to obtain WinCUPL (https://www.microchip.com/en-us/products/fpgas-and-plds/spld-cplds/pld-design-resources) to build your own equations. Unfortunately I do not know of a modern, open-source equivalent to work with these parts. Ideally use Windows or it can be got to work with Wine, as can the TL866 software.

Alternatively you can just burn the provided jed which will give you the default configuration which is similar in layout to a 256k Xplorer with the addition of the USB in the space above the ROM. (todo - document address layout). The source is provided. Its initially quite basic in scope but want to add to it to make use of the expansion IO connections provided, as well as switch functionality if desired.

Credit and Thanks
=================

To note: the PCB layout and design is the work of Nicolas Noble who was kind enough to design this for me. Thanks for this and the PIO-Breakout, without none of this would have been possible. Same for UNIROM (thanks sickle) which is indispensable for easy debugging of hardware like this. 

For more info or psx related chat - join us on psx.dev discord (http://psx.dev/)

