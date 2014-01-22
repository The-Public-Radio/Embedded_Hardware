# PR_Public_Radio
Created 2013.12.17
by Spencer Wright

## SYNOPSIS
The Public Radio is a project which spans industrial design, embedded systems design, and firmware.The files located within this project comprise a subset of the data reqired to fully complete ThePublic Radio, though efforts are being made to completely describe the project from top to bottom.

## CREDITS
The work herein is primarily a collaboration between Spencer Wright (http://pencerw.com) and Zach Dunham (http://zachdunham.com) though much ofit was adapted heavily from friendly sources. In particular, early versions of the firmware was adapted directly from Nathan Seidle et al (Sparkfun). Special thanks also goes to Todd Bailey (http://blog.narrat1ve.com/).

## LICENSE
In the interest of collaboration and good will, the files herein are offered for public use. Just don't be a jerk about it, etc., and do let us know if we've screwed something really big up (and, of course, we certainly have :).
At some point in the future, The Public Radio will be made commercially available. Inasmuch as it is feasible, we hope to continue to keep the design files and firmware here available for noncommercial use.


## PROJECT DESCRIPTION
The Public Radio is a single channel, single speaker FM receiver. 
As a piece of hardware, it was intended to be as simple as possible. One midrange speaker mounted inside a simple enclosure, with a single switched knob which controls power and adjusts volume.

Early on in the project, we planned on building a custom aluminum enclosure, but decided to protoype using an off-the-shelf container - a Ball brand mason jar. The enclosure requires one custom manufactured part: a replacement lid, to which the speaker, potentiometer, and electronics mount.

As I write this, the electronics consist primarily of off-the-shelf components: Arduino Pro Mini, Sparkfun breakout & evaluation boards. Our plan for the next few months includes stripping the hardware down to its barest components and discarding the prototyping tools we've used to get ourselves off the ground.

The firmware required to run The Public Radio is simple. The main Arduino sketch does the following:

* Defines three output pins
* Defines "channel" (FM frequency) and "volume" variables
* Instantiates the class Public_Radio
* Enables the Si4703 FM receiver chip
* Tunes to the defined frequency 
* Sets the volume

Also included are stripped down versions of the Si4703 written by Sparkfun and available at https://github.com/sparkfun/Si4703_FM_Tuner_Evaluation_Board. As my understanding of these is limited, I'll reserve description until a later date.

## CONTAINED HEREIN
* Industrial design files: These are mostly outdated, and were created in SolidWorks. Current versions, created primarily in Autodesk Inventor, still need to be folded into this repo.
* Embedded systems design files: Namely .brd, .sch, possibly gerbers. These will remain up-to-date, so long as I can keep ZD on his game :)
* Firmware: Arduino sketches, library files (header & source). 

## ELSE
I'm new to this game. Holler at me if I'm missing something.
