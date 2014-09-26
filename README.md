What's the Frequency, Arduino?
==================

What The Frequency is an Arduino-compatible frequency counter with a 4040N to extend the measurement range. Based on the [SparkFun]() [Frequency Counter Kit](https://www.sparkfun.com/products/10140), which in turn is based on [FunCount](http://www.nuxie1.com/guides/funcount-frequency-counter.html) by Nuxie.

My original goal was to understand how/why the ground shunt capacitors are necessary when one includes a crystal oscillator as a clock for a microcontroller. I wanted to see if the calculations I was making based on load capacitance had any bearing at all on the circuit, and by how much.

Three herds of bald yaks later, this almost-but-not-quite circuit is what I have. So it goes.

My modifications include:
* 4040 12-bit binary ripple counter to extend the measurable range beyond 8MHz
* Shrink the LCD down a bit
* Size the PCB to fit a [Hammond 1591XXA enclosure](http://www.hammondmfg.com/dwg2XX.htm)
* DC barrel jack and voltage regulator
* Some kind of external probe (this was a terrible idea)

In the process, I've leared more than a bit about how oscillators work, PCB design, and just how little my CS education prepared me for electrical engineering. ;)

As it stands, the project is incomplete: in my haste to get a damn board back
from OSHPark, I didn't thoroughly think through the design. There's a single
external probe connection...and no ground. And that adding those would upset
the measurement by adding a ton of extra capacitance, enough to swamp the
difference between a 22pF and a 30pF cap.

So, in the interest of building something useable but still having a modicum of
accuracy, I'm going to be including another Atmel chip (likely the ATTiny84,
since the 85 has the clock output on the same pin as the input for running a
crystal osciallator circuit) to get a given crystal circuit oscillating. By
calibrating and measuring the capacitance (and then accounting for that), I
should be have a test harness for the typical Pierce oscillator setup that
seems to get used a lot.

Licensed under the same Creative Commons BY-NC-SA 3.0 license as the kit I was
basing it on (though it's pretty much completely diverged at this point). I've been using CC-BY-SA-4.0 since I don't give a crap if you make money off this or not. Honestly, if you're using my board designs and selling them to people,
1. You're an idiot
2. You're gonna get sued when someone catches on fire (probably an orphanage)
3. I DISCLAIM ALL LIABILITY FOR THE USE OF THIS. USE AT YOUR OWN RISK.

YMMV, check with your doctor before taking Frequenizole, etc.
