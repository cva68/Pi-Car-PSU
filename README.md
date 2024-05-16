# Pi Car PSU
Hardware and software for a step-down power supply and associated controller, designed for powering a Raspberry Pi in a car. 
Useful for DIY Headunits, such as OpenAuto. This setup was run without issue for ~6 months, using a relay instead of toggling the 
ON/OFF pin of the step-down converter, but this should be functionally identical (although is untested).

## Features
- Conversion of car ignition signal to 5v and 3v3 logic level signals, with overvoltage protection
- Onboard microcontroller to allow for programmable startup and shutdown delays
- Simple design, can be constructed on perfboard

## Setup
- Construct the circuit: as described by the schematic and BOM in the schematic folder
- Flash the micrcrocontroller: I used the Arduino IDE for this, example code can be found in src.
- Create manager service for Raspberry Pi: A script that starts on boot should be created to watch for the ignition signal to fall low, then shutdown.
