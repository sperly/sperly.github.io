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
| 2 | Serial | A 65C52 Dual UART. |
| 3 | AL | Address and RD/WR logic. |
| 4 | EXP | Expansion Port. |

## CPU & Memory
To scale this part down I opted to remove the high memory socket and associated address logic. This simplified the board routing a lot. I will still be able to assess signal timing of the general data/address bus and basic address logic. Since I have selected a simple memory layout with a BIOS segment in the top I can already start to develop basic BIOS routines that will be compatible later on in stage 2/3.

![CPU Page](/img/stage1/cpu.png)

## Serial Controller
This is the final implementation of the serial controller and it allows me to be able to communicate with the µLind as soon as I develop basic BIOS routines for serial read/write.
- Serial 1 will be a USB port with a system console and will probably be the first to be developed.
- Serial 2 will be a serial periferal port or alternatively an extra Terminal (Hmm... Multi-user... NO! No feature creep here.)
The serial interupt will be hardbound to FIRQ to make the system as simple as possible.

![Serial Page](/img/stage1/serial.png)

## Address and Signal Logic
In stage 1 there will only be basic address logic, enough to be able to controll ROM, RAM and Serial Controller. But the RD/WR logic circuit will hopefully be able to trancend to later stages.
I will however be able to test both PLD's in some extent.

![Address Logic Page](/img/stage1/a-logic.png)

## Expansion Port
I will only incorporate one expansion port, mostly for debug purpouses and to be able to prototype other parts of stage 2/3 to make them more stable.
There will be a full data and address bus available and most of the logic signals created by the PLD's.

![Expansion Page](/img/stage1/expansion.png)

## Power
I will only implement a reset button in stage 1.

![Power Page](/img/stage1/power.png)

The schematics are available as a [PDF](/docs/schematics-stage1.pdf)  
And board layouts as well in [PDF](/docs/board-stage1.pdf)  

For KiCad project and drawings, see repository.
