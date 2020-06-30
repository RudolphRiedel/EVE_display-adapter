# EVE_display-adapter

These adapter boards connect a couple of FTDI/Bridgetek based FT81x/BT81x display modules with 3D-printer controller boards.
Basic support is present already in Marlin Bugfix 2.0x: ExtUI
I will add support for more displays to Marlin.
Recommended are 4.3" displays with 480x272 or 5.0" displays with 800x480.

The form factor with the two mounting holes allows replacing a RepRap gfx-display.

L-D5019-01-0x: to be used with displays from Matrix Orbital or Riverdi.

L-D5019-05-0x: to be used with displays from Crystalfontz.

The design source files are for Altium Designer.

But everything else to order boards and build them without AD is included as well.

The design of the "EXP1" header is optimised for the Fysetc Cheetah as I do have two of these and can therefore
test my changes in Marlin with my displays.

Also, the Cheetah is one of the very few 3D-printer controller boards that allows to use hardware-SPI with the display.

The adapter boards can also be configured to be used with at least the original CR-10/Ender-3 boards using software-SPI.

Recommended displays for now with L-D5019-01-0x:
- EVE3-43G https://www.matrixorbital.com/eve3-43g
- EVE3-50G https://www.matrixorbital.com/eve3-50g
- RVT43ULBNWC00 (RiTFT-43-CAP-UX) https://riverdi.com/product/ritft43capux/

Recommended displays for now with L-D5019-05-0x:
- CFAF800480E0-050SC https://www.crystalfontz.com/product/cfaf800480e1050sca11-800x480-eve-accelerated-tft

Before connecting any display to your controller board, make sure the board can take the additional load on the 5V!

And you need to use a flat-flex-cable with connections on opposite sides.


The D5019-01-04 and D5019-05-02 boards do work both, I was not satisfied with the loudness of the speaker though.

I ran a series of performance tests with two microcontroller boards and the same 5cm cable from these boards to the display-adapter boards.

One of the microcontroller boards was this: https://github.com/RudolphRiedel/SAMC21_one
The "SAMC21 One" has an ATSAMC21E18A running at 48MHz and 5.0V.

The other one has an ATSAME51J19A running at 120MHz and 3.3V.

The D5019-01-04 was tested with an EVE3-50G featuring a BT815 running at 72MHz.

The D5019-05-02 was tested with a CFAF800480E0-050SC featuring a FT813 running at 60MHz.

Both boards performed similar enough to present the numbers together.

ATSAMC21
- 12MHz max for reliable touch events
- 35MHz max for still displaying a stable image

ATSAME51
- 17MHz max for reliable touch events
- 40MHz max for still displaying a stable image

Note, I reduced the main clock to find the maximum read spead and overclocked the controllers for the maximum write speed.
Also the maximum write speed is out of spec for both the FT813 and the BT815.

As the target speed for these boards with Marlin is 8MHz on hardware-SPI and <2MHz on software-spi,
I conclude that the performance of the SPI on these boards is well within the desired limits.

D5019-01-05 with the 3.3V LDO works fine with a EVE3-43G that has been modified to dual supply.

D5019-05-03 is ordered, it has the same 3.3V LDO and speaker as the D5019-01-05.
