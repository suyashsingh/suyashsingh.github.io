---
title: Projects
description: Know more about projects done by Suyash Singh Bitti on Embedded Systems, Linux System Programming, Linux Kernel Development, PCB Design using KiCad, RTOS, CAN and more. Here are some of the projects.
layout: default
order: 3
---
I have worked on projects on firmware development, microcontroller board design, linux device drivers, linux systems programming, socket programming, etc. Here are some of the projects that I  have done, the list isn't exhaustive though.

## STM32F070 Board
<span class="badge badge-primary">Work in Progress</span><br>
<a href="https://www.st.com/en/microcontrollers-microprocessors/stm32f070f6.html" title="Product Page for STM32F070F6 from ST Microelectronics" target="_blank">STM32F070F6</a> is a `32-Bit ARM Cortex M0` microcontroller from ST micro. The micro comes in 
`TSSOP` package which makes it easy to hand solder.

My intention for designing the board was to practically learn PCB desgin using
<a href="https://kicad-pcb.org/" title="Home Page of KiCad PCB EDA design suite" target="_blank">KiCad</a>. However, the project taught me much more than just pcb design. It gave me gimplse of the entire project development life cycle that goes into desgining a board from a concept: 

+ Capturing Specifications for the project
+ Schematic Design for the Project
+ Designing footprint libraries for components not avaialable in standard libraries
+ Physical Routing
+ Design workflow in KiCad
+ Selection of components for the project
+ Generating gerbers and getting board fabricated from Board house
+ Generating BOM and getting components ordered from Component Vendors: I had a few setbacks
in this stage. Some of the components went out of stock and got back ordered from
the time of schematic design to sending gerbers to fab house.
+ Board checks after fabrication

As of now the project is currently in hold. I would have to take out time to get
it done soon. <a href="https://github.com/suyashsingh/stm32f070-board" title="hardware design files for STM32F070 board designed by Suyash Singh Bitti" target="_blank">Here is the link to the project page on github</a>.

## Realtime CAN Data Dashboard
This was my major project for completion of PG Diploma in Embedded system Design
at C-DAC. There were two units in the project: a data acquisition unit and 
a data display unit. The two boards were interconnected via `CAN`. The data acquisition
unit ran `FreeRTOS` for managing the tasks. `IPC mechanism: Event registers` was used
for synchronising producer(tasks that reads sensor) and consumer(task the sends 
CAN messages) tasks in the system.

You can find more about the project on <a href="https://www.linkedin.com/in/suyash-singh-bitti/" title="More information on Real Time CAN Dashboard project on my linkedin page" target="_blank">projects section of my linkedin page</a>.