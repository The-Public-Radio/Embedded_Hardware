# PR_Public_Radio
Created 2013.12.17
by Spencer Wright
Updated by Zach Dunham 2014.08.01

## LICENSE
In the interest of collaboration and good will, the files herein are offered for public use. Just don't be a jerk about it, etc., and do let us know if we've screwed something really big up:).
At some point in the future, The Public Radio will be made commercially available. Inasmuch as it is feasible, we hope to continue to keep the design files and firmware here available for noncommercial use.


## PROJECT DESCRIPTION
The Public Radio is a single channel, single speaker FM receiver. 
As a piece of hardware, it was intended to be as simple as possible. One midrange speaker mounted inside a simple enclosure, with a single switched knob which controls power and adjusts volume.


## SYNOPSIS
The Public Radio is a project which spans industrial design, embedded systems design, and firmware. The files located within this project comprise a subset of the data reqired to fully complete ThePublic Radio, though efforts are being made to completely describe the project from top to bottom.

## CREDITS
The work herein is primarily a collaboration between Spencer Wright (http://pencerw.com) and Zach Dunham (http://zachdunham.com) though much of it was adapted heavily from friendly sources. In particular, early versions of the firmware was adapted directly from Nathan Seidle et al (Sparkfun). Special thanks also goes to Todd Bailey (http://blog.narrat1ve.com/).

## Board and Layout

PR500X is a circular PCB with an OD of 70mm and a 23mm circular cutout at its center. The cutout is designed such that the radio's speaker drops partly through the PCB; its backside passes through the cutout allowing the solder lugs to be soldered directly to the board. The antenna and trim pot are additionally mounted directly to the board and pass through the top of the lid. Two sets of two AA battery clips are mounted on the bottom side of the board to house the two AA batteries.

Si4831 FM Receiver

PR500X utilizes the Si4831 chip in a 24 pin, SSOP package. Si4831 is a mechanically tuned digital CMOS AM/FM receiver. PR500X only utilizes the FM functionality of the radio. Connections are as follows:

Pins 1 & 2 - indicate stereo signal and station reception, respectively. Pin 1 is left floating since we are only functioning in mono mode. Pin 2 is tied high via R4 to set the radio in “volume mode” as opposed to “bass/treble mode” and tied high through R5 in series with an LED to indicate reception.
Pins 2 & 3 - form the tuning circuit of the radio along with C1, C2, trimpot R10, R1 and R3. Varying the resistance between these to pins varies the center frequency in the FM range. The radio calls for 413K at 1% between the band select pin and pin 1 of the trim pot. To keep within this tolerance we broke the 413K resistor into two resistors at 412K and 1K values.
Pin 5 - is the band select. According to the data sheet, pin 5 wants to see 77K resistance to ground to set the band select at 87-108MHz
Pin 6,7 - NC
Pin 8 - is the FMI pin which consists of an ESD protection diode and inductor L1 to ground inline with a capacitor, C3 to pin 8 forming a high pass filter. Additionally, because our design places the antenna roughly 30 mm from pin 8, and to limit noise on the FMI line, we’ve placed restricts on both the top and bottom layer ground planes around the antenna trace.
Pin 9, 10, 11, 12 - tied to ground. Pin 9 is the RFGND, Pins 10, 11, 12 are part of the AM circuit tied to ground. Note, our testing with showed no loss of FM reception tying the AM to ground or leaving it floating.
Pin 13, 14 - also ground pins
Pin 15 - is the reset pin, tied high through R6 inline with C4 to ground
Pin 16, 17 - volume or bass/treble control. By tying pin 2 high we’re utilizing volume mode, and by tying pins 16 & 17 to ground we’re setting the output to maximum volume.
Pin 18 & 19 - are pins for the external 32.768 KHz oscillator with necessary loading caps (C6 and C8) tied to ground.
Pins 20, 21, 22 - are the power and bypass pins. Pins 20 and 21 - VDD1 and VDD2 - are connected to VCC through C5, C7. The other leg of C5 and C7 are connected to pin 22 which is the IC’s internal bypass pin. Additionally, to mitigate noise C5 and C7 are inline with a ferrite bead connected to VCC.
Pins 23 and 24 - left out and right out signal to the audio amplifier
TPA2005d1 1.4 W Mono Audio Amp

PR500X uses this class-d audio amp to power its 1” full range driver.

Pin 1 - shutdown pin which is tied high through R8 inline with C10 to ground for a roughly 1/4 second delayed power up.
Pin 2 - NC
Pin 3 - positive differential input from the output of the radio connected via coupling capacitor C9 and gain setting resistor R7, for a gain of roughly 6.
Pin 4 - negative differential input, same values as pin 3
Pin 5 - positive output, connected to the speaker
Pin 6 - VDD connected to VCC through decoupling capacitors C12 and C13 along with a ferrite bead, L2
Pin 7 - GND
Pin 8 - negative output, connected to the speaker
Notes!
PR5006 has no reverse polarity protection. The bottom solder mask design aims to provide the correct battery orientation. The following version will most likely incorporate a synchronous rectifier
Update: PR5007- includes reverse polarity protection through implementing a mosfet in the PWR line.  


Early on in the project, we planned on building a custom aluminum enclosure, but decided to protoype using an off-the-shelf container - a Ball brand mason jar. The enclosure requires one custom manufactured part: a replacement lid, to which the speaker, potentiometer, and electronics mount.


## CONTAINED HEREIN
* Industrial design files: These are mostly outdated, and were created in SolidWorks. Current versions, created primarily in Autodesk Inventor, still need to be folded into this repo.
* Embedded systems design files: Namely .brd, .sch, possibly gerbers. These will remain up-to-date, so long as we can stay on our game:)
* Firmware: Arduino sketches, library files (header & source). 

