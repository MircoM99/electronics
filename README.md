# Electronics

This repository contains all the files for the design of all the electronics subsystems of the project.

# Repository's Structure

The repository is structured in two main folders of similar arrangement:

- `Test Stand`
  - `\Hardware`
  - `\Software`
  - `\Documents`
  
- `Avionic` 
  - `\Hardware`
  - `\Software`
  - `\Documents`
  
## Hardware

The Hardware folder contains all the project files dedicated to the design of the corrisponding PCB. The Project files are build using the open source software [Kicad](https://kicad.org/). After installing the software, open the project file with the `.pro` extension that can be found in the directory path:

- `Test Stand\Hardware\Test Stand PCB\Test Stand PCB.pro`
- `Avionic\Hardware\Avionic PCB\Avionic PCB.pro`

This folder also contains all the Symbols and Footprint libraries used. 

- `Breakout_Test_Stand_PCB.lib`
- `Test Stand PCB Breakout.pretty`

## Software

The software folder contains all the files used to develop the corrisponing subsystem's software.
The files are built using [Microsoft Visual Studio Code](https://code.visualstudio.com/) and the extension [PlatformIO](https://platformio.org/).

The main framework used remain the Arduino Framework

![Thrust Logo](https://github.com/thrust-team/electronics/blob/main/Test%20Stand/Figures/logo_thrust.png)


