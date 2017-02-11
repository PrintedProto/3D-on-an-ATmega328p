My [renderer](https://www.thanassis.space/renderer.html) is quite a "beast";
supporting many rendering modes. I've almost forgotten what it was like when
I begun playing with 3D code, 2 decades ago...

...so it was time for a trip "down memory lane": I implemented the points-only
mode on a "naked" ATmega328P sitting on a breadboard, and had it drive an
OLED screen via SPI at the magnificent resolution of 128x64 :-)

This was fun :-)

<center>
<a href="https://drive.google.com/open?id=0B2wfdiRsjeLOb0FEUDItaGFxTVE" target="_blank">
<img src="contrib/3DFX.jpg">
</a>
</center>

Points of note:

- Fixed point calculations, of course (8 bits for the decimal part)
- I stored and read the statue data from the .text segment. Even though
  the ATmega328P has 32KB of flash available to store the program
  code, it only has 2K of RAM. So I use the flash storing the code to
  also store the constant data of the XYZ point coordinates.
- Bonus "distance LED": shines brightly when the statue gets close :-)
- Conditionally outputs FPS info to serial port.

I never did SPI HW before - let alone on a tiny ATmega328P on a breadboard.
And here I had to do it twice: the ATmega328P drives the OLED, but it
is itself programmed via the SPI pins of the "big brother" siting on
the right of the breadboard: a Raspberry PI2 is programing the ATmega328P's
flash via avrdude. And yes, the pins are shared.

All in all - nice, clean fun.

Thoroughly enjoyed playing with HW again :-)
