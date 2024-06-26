---
layout: page
title: MicroLind Stage 1
subtitle: An initial build
---

## Scaling Down
To make the routing more managable I desided to make it in stages and in this, the first one, I will focus on getting the processor and memory up and running.

![Stage1 Motherboard](/img/stage1/ml-stage1.png)

During this stage I will be able to test that Read/Write logic and signal timing is correct between the most important parts of the system: CPU, ROM, RAM and serial interface.
The board will be able to communicate with a serial-USB bridge so I can connect it to my regular computer and hopefully receive data from µLind.
This is Stage 1 design:

![Master Page](/img/stage1/master.png)
To make it manegable there are only 4 parts of the stage 1 layout:

| Part | ID | Info |
| :---: | :--- | :--- |
| 1 | CPU | The main cpu and the ROM and RAM. |
| 2 | Serial | A Dual UART. |
| 3 | AL | Address and RD/WR logic. |
| 4 | EXP | Expansion Port. |

## CPU & Memory
To scale this part down I opted to remove the high memory socket and associated address logic. This simplified the board routing a lot. 
I will still be able to assess signal timing of the general data/address bus and basic address logic. 
Since I have selected a simple memory layout with a BIOS segment in the top I can already start to develop basic BIOS routines that will be compatible later on in stage 2/3.
The design is based on a 6809 but a 6309 might be a simple upgrade. And to make it small and simple I choose a 512kB static RAM. The ROM is an EEPROM (to make it easy when developing BIOS) but it is write protected in the design.
I have un ide to make it so the USB interface can set it in "Write enable" mode (There are some GPIO on the USB interface circuit, that can be controlled from the host computer). 
The idea is to have an host application on the PC that sets the ROM in WE and sends a new BIOS image that an onbard application can program into the ROM and verify.

![CPU Page](/img/stage1/cpu.png)

## Serial Controller
This is the final implementation of the serial controller and it allows me to be able to communicate with the µLind as soon as I develop basic BIOS routines for serial read/write.
- Serial 1 will be a USB port with a system console and will probably be the first to be developed.
- Serial 2 will be a serial periferal port or alternatively an extra Terminal (Hmm... Multi-user... NO! No feature creep here.)
The serial interupt will be hardbound to FIRQ to make the system as simple as possible.

![Serial Page](/img/stage1/serial.png)

## Address and Signal Logic
In stage 1 there will only be basic address logic, enough to be able to controll ROM, RAM and Serial Controller. 
But the RD/WR logic circuit will hopefully be able to trancend to later stages.
I will however be able to test both PLD's in some extent. When we initially started elaborating on the idea of an 8-bit computer we made a design of an address logic entirely with basic logic chips, but I realised very soon that it would be near impossible to place/route in the designated space. 
So the natural selection was simple PLD or GALs, wich I already had at home.

![Address Logic Page](/img/stage1/a-logic.png)

## Expansion Port
I will only incorporate one expansion port, mostly for debug purpouses and to be able to prototype other parts of stage 2/3 to make them more stable.
There will be a full data and address bus available and most of the logic signals created by the PLD's.
I will use this port to test other parts of the system that will be incorporated in later stages. *Fingers crossed*

![Expansion Page](/img/stage1/expansion.png)

## Power
I will only implement a reset button in stage 1. In later stages I will add a mechanism to be able to press a button to start the system, and to write a bit in a register to turn it off or reset. This will give the operation system a possibility to implement shutdown and restart functionality.

![Power Page](/img/stage1/power.png)

The schematics are available as a [PDF](/docs/schematics-stage1.pdf)  
And board layouts as well in [PDF](/docs/board-stage1.pdf)

KiCad schematic & layout will be coming soon.
