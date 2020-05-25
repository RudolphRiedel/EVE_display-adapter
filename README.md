# EVE_display-adapter

These adapter boards connect a couple of FTDI/Bridgetek based FT81x/BT81x display modules with 3D-printer controller boards.
Basic support is present already in Marlin Bugfix 2.0x: ExtUI
I will add support for more displays to Marlin.
Recommended are 4.3" displays with 480x272 or 5.0" displays with 800x480.

The form factor with the two mounting holes allows replacing a RepRap gfx-display.

L-D5019-01-04: to be used with displays from Matrix Orbital or Riverdi.
L-D5019-05-02: to be used with displays from Crystalfontz.

The design source files are for Altium Designer.
But everything else to order boards and build them without AD is included as well.

The design of the "EXP1" header is optimised for the Fysetc Cheetah as I do have two of these and can therefore
test my changes in Marlin with my displays.
Also, his is one of the very few boards that allows to use hardware-SPI with the display.
The adapter boards can also be configured to be used with at least the original CR-10/Ender-3 boards using software-SPI.

Recommended displays for now with L-D5019-01-04:
- EVE3-43G https://www.matrixorbital.com/eve3-43g
- EVE3-50G https://www.matrixorbital.com/eve3-50g
- RVT43ULBNWC00 (RiTFT-43-CAP-UX) https://riverdi.com/product/ritft43capux/

Recommended displays for now with L-D5019-05-02:
- CFAF800480E0-050SC https://www.crystalfontz.com/product/cfaf800480e1050sca11-800x480-eve-accelerated-tft


Note, I ordered the released revisions of these boards today, for at least the next two weeks the status of these is: untested!
I have the previous revisions of these boards up and running and feel confident enough to release this,
but there is a chance that these might need annother revision...

Before connecting any display to your controller board, make sure the board can take the additional load on the 5V!
And you need to use a flat-flex-cable with connections on opposite sides.
