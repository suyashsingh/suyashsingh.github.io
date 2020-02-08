---
title: Projects
layout: default
order: 3
---

## STM32F070 Board
[STM32F070F6](https://www.st.com/en/microcontrollers-microprocessors/stm32f070f6.html) 
is a `32-Bit ARM Cortex M0` microcontroller from ST micro. The micro comes in 
`TSSOP` package which makes it easy to hand solder.

My intention for designing the board was to practically learn PCB desgin using
[KiCad](https://kicad-pcb.org/). However, the project taught me much more than just pcb design. It gave me
gimplse of the entire cycle that goes into desgining a board from a concept: 

+ Designing Specifications
+ Schematic Design
+ Designing footprint libraries for components not in standart libraries
+ Physical Routing
+ Design workflow in KiCad
+ Selection of components
+ Generating gerbers and getting board fabricated from Board house
+ Generating BOM and getting components ordered from Component Vendors: I had a few setbacks
in this stage. Some of the components went out of stock and got back ordered from
the time of schematic design to sending gerbers to fab house.
+ Board checks after fabrication

As of now the project is currently in hold. I would have to take out time to get
it done soon.

[Here is the link to the project page on github](https://github.com/suyashsingh/stm32f070-board).

## Realtime CAN Data Dashboard
This was my major project for completion of PG Diploma in Embedded system Design
at C-DAC. There were two units in the project: a data acquisition unit and 
a data display unit. The two boards were interconnected via `CAN`. The data acquisition
unit ran `FreeRTOS` for managing the tasks. `IPC mechanism: Event registers` was used
for synchronising producer(tasks that reads sensor) and consumer(task the sends 
CAN messages) tasks in the system.

You can find more about the project on [projects section of my linkedin page](https://www.linkedin.com/in/suyash-singh-bitti/).