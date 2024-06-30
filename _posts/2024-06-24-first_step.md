---
layout: post
title: First step for the µLind project
subtitle: A long and windy road to insanity
gh-repo: sperly/microlind
gh-badge: [star, fork, follow]
tags: [µLind, 6809]
comments: true
---

Today I finally finished the first stage of the µLind computer! Yeay!
After several hours of designing and discussing design options with my partner in crime, my son, I have finally sent the first stage for fabrication. The first stage you say, what is that?
Well after several months of grinding in KiCad I suddenly realised that I was bored with the project, just because I did not get anywhere. I wanted to play and program the system!
So I took what I had in design and desided to make it in 3 stages do handle smaller increments. This will also lead to a much easier bord bringup when ther is less things that can go wrong.
So what are these 3 stages then:

| Stage | Content | Finished? |
| :------ |:--- | :--- |
| 1 | CPU, ROM, Low RAM, Serial Port and one expansion port (To debug easier) | Done |
| 2 | Stage 1 + High Ram, Address Logic (For banking etc.), Interupt Logic, three expansion ports (Audio, Video and External) | In progress |
| 3 | Stage 2 + PS2 (Mouse & Keyboard), Joystick Ports, Internal Storage Option (CF) | Designed |

Each stage will let me test all implemented parts and update next stage with any mistakes found during testing.

{: .box-note}
**Note:** When each stage is finished I will publish any gerbers for that stage (The same I send to fab).
