# GURPS BeamGen

## Outline
This is a Python3 program that automates the rules from the article *Eidetic Memory: Blaster & Laser Design* from **_Pyramid #3/37_**. Input is via text in the terminal, command line or shell and output is a text block in the same interface with an option for output via XML data in the format recognised by [GURPS Character Sheet](http://gurpscharactersheet.com). When inputting formating, please take care to spell and format input exactly as given in the prompts, as there is currently little to no error handling or correction for incorrect inputs.

## Installation and Running
1. Open your terminal or command line and navigate to the folder where you want to intall BeamGen.
2. Clone the github repository to this folder by entering `git clone https://github.com/GURPSGen/BeamGen`
3. Execute the BeamGenerator.py script in Python by typing `python BeamGenerator.py`. Python2 *will not work*; you may need to use the `python3` command instead of `python`, depending on your operating system.
4. Follow the command line prompts.

If using the GCS output, the objects are written to the BeamGen.eqp file. Do not move this file as the GCS output functionality will break if it is not there. Instead, open this file in GCS and copy over any items you want to keep into character sheets or custom GCS equipment libraries.

## Current Features
* All released beam types, focal arrays and power cells. The pistol, rifle and beamer configurations are implemented, the cannon configuration is not.
* Blue-green and ultraviolet high-energy lasers.
* Continuous- and pulsed-beam lasers, including dual-mode lasers that can switch between both modes.
* Scatterbeams ("beam shotguns"), including dual-mode scatterbeams that can switch between both modes.
* Nonrechargeable power cells.
* Beam types from **_GURPS Ultra-Tech_** not represented in the article (all are implemented but only electrolasers, plasma flamers and plasma guns are reasonable; see Known Bugs below).
* Weapon quality grades and features: Cheap, Expensive, Hotshotted, Disguised, Styled, Rugged, Fine/Very Fine (Accurate) and Fine/Very Fine (Reliable).
* Randomly-generated beam weapons (this feature is not yet complete; see Planned Features below).
* Automated output into XML format for use with GURPS Character Sheet.

## Planned Features
* Beam cannon.
* Complete random generation (currently rate of fire, power cells, and qualities and features are not randomised).
* Weapon accessories, e.g. smart grips and scopes.
* Additional third-party beam types, e.g. plasma weapons from [Plasma Guns, Re-Energised!](http://gurb3d6.blogspot.co.uk/2016/08/plasma-guns-re-energized.html)
* Graphical user interface (GUI).
* Compilation into a standalone executable that doesn't need to be run from the terminal/command line.

## Bug Reports
A program like this has a large amount of things going on internally and although I try to do proper unit testing and integration tests when adding new features, I make mistakes. If you encounter any errors, bugs or inaccuracies in the program, please create a [new issue on the Github page](https://github.com/GURPSGen/BeamGen/issues). If the error produced an error message or traceback, please include this. A traceback in the terminal/command line will normally begin with `Traceback (most recent call last):`. 

## Known Bugs
* (Original article) The number of shots a weapon could fire was prone to inaccuracies due to the complicated nature of adjusting power cell capacity based on TL. Although **_GURPS Ultra-Tech_** does mention an increase in power cell capacity per TL, this behaviour is not represented or even mentioned in the statistics for beam weapons, so it has been removed for now, using power cell capacities that are static and based on the TL at the weapon's introduction. It may be re-added in the future, especially if increased shot capacity by TL is confirmed as an intended feature by the designers.
* (Original article) Trying to create copies of weapons from **_GURPS Ultra-Tech_** will provide results that are not exactly the same, though the variations are small, typically around 0.2lbs or $100 off. This was acknowledged by the author.
* (Original article) Rifles using rainbow laser, X-ray laser or graser beams have about half the range of equivalent weapons in **_GURPS Ultra-Tech_**. This has been fixed with a 'fiddle factor' that is marked clearly in the code.
* Although the program allows you to generate several weapons in succession, keywords are not cleared between weapons. E.g. making a cheap weapon followed by an expensive weapon will produce a weapon that is both cheap and expensive. For the time being, the work around for this is to restart the program between uses.
* Force beamers have some dramatic inaccuracies in weight and range. Whether this is an issue with the article or the program has not yet been verified.
* Neural, sonic screamer and sonic stun beam weapons have weights and costs totally incongruous with those listed in **_GURPS Ultra-Tech_**. This is due to the properties for these weapons varying significantly between each weapon configuration. The only way to fix this would be to define the properties separately per configuration.
* When writing weapons that have linked or alternate fire modes (electrolasers, dual-mode beam/pulse lasers and dual-mode scatterbeams) to a GCS file, only the primary firing mode is added. The alternate fire mode is displayed when using the terminal output.

## Legal Information and Credits
GURPS is a trademark of Steve Jackson Games, and its rules and art are copyrighted by Steve Jackson Games. All rights are reserved by Steve Jackson Games. This game aid is the original creation of CTA and is released for free distribution, and not for resale, under the permissions granted in the [Steve Jackson Games Online Policy](http://www.sjgames.com/general/online_policy.html).

While I don't know whether I am permitted to add a Creative Commons license to my work in addition to the required Steve Jackson Games legal notice, I would like anyone who looks at or modifies this sourcecode to act in the spirit of the [Attribution-NonCommercial-ShareAlike (BY-NC-SA)](https://creativecommons.org/licenses/by-nc-sa/4.0/) version of the Creative Commons license.

The cover image is from a promotional image of Han Solo from *Star Wars: A New Hope*.
