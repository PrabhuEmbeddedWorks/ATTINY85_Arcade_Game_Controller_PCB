# ATTINY85 Arcade Game Controller PCB

## Features
- ATtiny85 microcontroller based embedded system
- 0.96 inch SSD1306 I2C OLED display
- Three push buttons for game control (Left, Right, Jump/Fire)
- Buzzer for audio feedback
- CR2032 coin cell battery powered
- Slide switch for power control
- Custom controller shaped PCB outline
- 3D PCB visualization using KiCad
- Custom KiCad footprint library
- Autorouting using FreeRouting plugin

## Tools and Technologies

| Tool | Purpose |
|-----|--------|
| KiCad 8.0 | Schematic design and PCB layout |
| FreeRouting Plugin | Autorouting of PCB tracks |
| Java JRE | Runtime required for FreeRouting |
| Inkscape | Creating custom PCB outline (DXF import) |

## System Architecture

The system is organized into four functional modules.

### Power Management

The system is powered using a CR2032 coin cell battery. A slide switch is used to control power to the board, and an LED indicator provides visual confirmation that the system is powered.

### Microcontroller

The ATtiny85 microcontroller serves as the central processing unit of the system. It handles button input processing, OLED display communication, buzzer control, and execution of the game logic.

### Display Interface

The display module used in the project is a 0.96 inch SSD1306 OLED. Communication between the display and the ATtiny85 is implemented using the I2C protocol. This allows the system to control the display using only two communication lines: SDA and SCL.

### Input Controls

Three push buttons are used as user inputs:

- LEFT button
- RIGHT button
- JUMP/FIRE button

Each button uses a pull-down resistor to ensure a stable logic level when the button is not pressed.

### Audio Output

A small buzzer is connected to the microcontroller to provide sound feedback during gameplay.

### Programming Interface

A programming header is included to allow firmware programming of the ATtiny85 using an ISP programmer.

## PCB Design

The PCB layout was created using KiCad 8.0. A custom controller-shaped outline was designed by importing a DXF graphic into the Edge.Cuts layer.

Component placement was optimized for usability and routing efficiency:

- OLED display positioned at the top center
- Control buttons placed along the top edges
- ATtiny85 microcontroller positioned in the lower section
- Buzzer placed centrally for balanced layout
- Coin cell battery holder placed on the backside of the PCB

Signal routing was performed using KiCad’s interactive router, and automated routing was also tested using the FreeRouting plugin.

## Custom Component Libraries

Several components used in the project were not available in the default KiCad libraries. Custom footprints were created for the following components:

- SSD1306 OLED display module
- CR2032 battery holder
- SS-12D00 slide switch

Footprint and 3D model integration involved the use of the following file formats:

- `.kicad_mod` for PCB footprints
- `.wrl` and `.step` for 3D models

3D model alignment was achieved by adjusting rotation and offset parameters within the KiCad footprint editor.

## 3D PCB Visualization

KiCad’s 3D viewer was used to validate mechanical alignment and component placement. This allowed verification of OLED placement, switch orientation, battery holder position, and overall board structure before manufacturing.
