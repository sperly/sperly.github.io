---
layout: page
title: MicroLind
subtitle: A foray into 8-bit computer design
---

The µLind project started in my head many year ago when my oldest son showed his first intrest in electronics. But in reality it came to life when I was gifted a large box of old electronics.
In this box, which I gave to my now 15 year old son to rummage through, there was 3 micro processors I myself had never been in contact with before. I am an avid Commodore user so I mostly used 6502/6510 and the Z80 on occation.
This new facinating processor sparked my electronic design intrest again! My son plowed through the datasheet for the processor and we started laying down some design criterias:

- Easy to solder by hand.
- All thruhole components.
- No exotic (at least too exotic) components, must be able to find them.
- Usb port terminal (to program and to interact through).
- Handle at least 1Mb- 
- Have joystick interface (C64 compatible).
- Have keybord interface (PS2).

Extended features that would be cool to have:

- Mouse interface (PS2).
- "Unlimited" storage (CF or Floppy).
- Be expandable, eg. have a multi-capable expansion port.

Me and my son started hooning in on what would be the first draft of µLind, our 6809 based 8-bit computer.
After a few months of fiddeling in KiCad I had a schematic of something that could be called a computer and on further discussion with my son I felt ready to layout.
I desided that this was not challenging enough, so I put some constraints on the layout:

- Fit in a regular Mini-ITX case, but not neccessarily with the same backplate (I just wanted a reference board with an suitable size to help me base a case on a current mini-itx box).
- All user connectors on the front (PS2, joystick and CF).
- Expansion port on the side to be able to chain expansion modules.
- A sturdy USB-B connector to feed power and to connect to console.
- 2 expansion modules with connectors on the back (Audio board & Video board).

![System Architecture](/img/system-architecture.png)

I boiled it down to an "simple" architecture shown above.

With this in mind and a "feature complete" computer I started doing the actual pcb layout. This task was far more daunting than I would have guessed, I could not get it done.

![Motherboard-Goal](/img/motherboard.png)

After several weeks of just staring at the mostly empty board I got the excellent idea of doing the layout in stages:

| Stage | Content | State |
| :------ |:--- | :--- |
| [Stage 1](/microlind/ml-stage1.md) | CPU, ROM, Low RAM, Serial Port and one expansion port (To debug easier) | Finished & Ordered |
| [Stage 2](/microlind/ml-stage2.md) | Stage 1 + High Ram, Address Logic (For banking etc.), Interupt Logic, three expansion ports (Audio, Video and External) | Layout in progress |
| [Stage 3](/microlind/ml-stage3.md) | Stage 2 + PS2 (Mouse & Keyboard), Joystick Ports, Internal Storage Option (CF) | Designed |

No more than 3 days after this desicion I finished with the general layout and routing. I now let my son review the schematics and the routing with datasheets of all components.
After 3 reviews and revisions we desided to order the board and call stage 1 closed.

This is where the project is today, avaiting hardware to test and start to develop a BIOS on.

