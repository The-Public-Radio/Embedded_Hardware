# PR_Public_Radio
Created 2013.12.17
by Spencer Wright |
Updated by Spencer Wright 2015.01.21

## LICENSE
In the interest of collaboration and good will, the files herein are offered for public use. Just don't be a jerk about it, etc., and do let us know if we've screwed something really big up:).
The Public Radio is licensed under a Creative Commons Attribution 4.0 License. For more info, visit https://creativecommons.org/licenses/by/4.0/


## PROJECT DESCRIPTION
The Public Radio is a single channel, single speaker FM receiver. 
As a piece of hardware, it was intended to be as simple as possible. One midrange speaker mounted inside a simple enclosure, with a single switched knob which controls power and adjusts volume.


## SYNOPSIS
The Public Radio is a project which spans industrial design, embedded systems design, and firmware. The files located within this project comprise a subset of the data reqired to fully complete ThePublic Radio, though efforts are being made to completely describe the project from top to bottom.

## CREDITS
The work herein is primarily a collaboration between Spencer Wright (http://pencerw.com) and Zach Dunham (http://zachdunham.com) though much of it was adapted heavily from friendly sources. In particular, early versions of the firmware was adapted directly from Nathan Seidle et al (Sparkfun). Special thanks also goes to Todd Bailey (http://blog.narrat1ve.com/) and Andy Warner (https://github.com/andyw-lala?tab=activity)

## Board and Layout

PR90XX is a circular PCB with an OD of 70mm and a 23mm circular cutout at its center. The cutout is designed such that the radio's speaker drops partly through the PCB; its backside passes through the cutout. The antenna and trim pot are additionally mounted directly to the board and pass through the top of the lid. Two sets of two AA battery clips are mounted on the bottom side of the board to house the two AA batteries.

Early on in the project, we planned on building a custom aluminum enclosure, but decided to protoype using an off-the-shelf container - a Ball brand mason jar. The enclosure requires one custom manufactured part: a replacement lid, to which the speaker, potentiometer, and electronics mount.


## CONTAINED HEREIN
* Embedded systems design files: Namely .brd, .sch, possibly gerbers. These will remain up-to-date, so long as we can stay on our game:)
* Firmware: Arduino sketches, library files (header & source). 
* Miscellaneous tools: This currently comprises of just a shell script used to create CSVs from EAGLE exports, which generally suck. The script is okay, though.

