Like A G35
==========

An alternate driver for GE Christmas lights that's an Arduino shield. Based on the 
[G35Arduino project](https://github.com/sowbug/G35Arduino). These instructions are 
for the G35 side of the board, built as of [tag v0.1](https://github.com/sowbug/like-a-g35/zipball/v0.1).

BOM
===

* The board. Have it manufactured by [OSH Park](http://oshpark.com/).
* A micro-USB connector, FCI part [10118193-0001LF](http://www.mouser.com/ProductDetail/FCI/10118193-0001LF/?qs=%2fha2pyFadujdGYiRLwYbSOKALiSo%252bepJVRcIj9hkdZjVBFUo3HGQQw%3d%3d).
* At least one [5.08MM 3-pin terminal block](http://www.mouser.com/ProductDetail/TE-Connectivity-AMP/282837-3/?qs=sGAEpiMZZMvlX3nhDDO4AEiipl7BG01uQiHyL2Oob2I%3d). The green things with screws.
* A bunch of snappable pin headers -- enough to make the usual Arduino 8/8/6/6 combo.
* Recommended: an Arduino, both for using with the shield, and during assembly as a frame for getting
the header pins straight.

Initial Usage
=============

1. Clone [G35Arduino](https://github.com/sowbug/G35Arduino) following the placement instructions there.
1. Fire up your Arduino IDE.
1. Change any of the examples to use pin 8 for the first strand, pin 9 for the second strand, and pin 10
if you're a big spender and have three G35 strands.
1. Program your Arduino.
1. Plug in the shield. Look for smoke. If you're more careful than I am, confirm that 5V is reading 5 volts,
GND is reading zero volts, and Data on the G1 header is putting out a digital signal.
1. Hook up the first strand of lights to the three-terminal header marked G1. Right before you cut off the
controller, as you were looking at the first light you saw +/D/-, left to right. See the
[V+/D/V- diagram](http://www.deepdarc.com/2010/11/27/hacking-christmas-lights/). Hook up + to 5V, the
middle wire to Data, and - to GND.
1. If you still have your Arduino plugged into your computer, by now you should be seeing at least the test
pattern on your strand. If not, check your wiring and assembly.

Production Usage
================

* The reason there is a USB connector on the shield is that the Arduino's power is limited to 500mA, or
else you risk blowing its polyfuse. Even a single G35 strand can use more than an amp. But the shield's USB
connector is a *direct* connection to the light power lines. So as long as you can find a power adapter
that fits the micro-USB plug (should be easy; lots of power adapters these days have type-A USB) and
provides regulated 5V, you can pump as much current as you want into this shield (it'll also power the
Arduino, of course). *BEWARE* that in exchange for this freedom, you can easily kill your lights and your
Arduino. You *must* provide *a regulated 5-volt supply*. Not 4.5, not 6, not 9, not 12. I don't care if your
7.5-volt supply worked fine with your Arduino. If you hook it up to this USB socket, all your hardware will
die and you might burn down your house.
* I've soldered the stranded copper wire of my lights so that they don't tarnish too much over the winter.