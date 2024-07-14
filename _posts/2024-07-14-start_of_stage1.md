---
layout: post
title: Start of Stage1
subtitle: Making things run
gh-repo: sperly/microlind
gh-badge: [star, fork, follow]
tags: [µLind, Stage1, Troubleshoting]
comments: true
---

The first prototype boards for stage 1 arrived a week ago and I started soldering components emediately.
I made a small test program, just to see what happens and programmed the EEPROM and the GALs accordingly.
And.... Nothing! I should have known that nothing goes according to plan in diy electronics.  

But since I actually measured every pin and connection on the board before any circuits where added, I, with at least with a small certaincy, knew that the board was ok and nothing would smoke.  

Soooo... What was wrong then? I started with the crystal and saw very little signal from it, so I assumed my load capacitor calculations where wrong. But after trying several different values I threw in the towel and ripped it out and bodged in an ocillator instead. Now I at least had a stable clock in to the processor (at least I thought so). But still no clock on the E pin out...  

I read some more and measured some more and my son read some more and came and explained to me that the MRDY pin should be pulled high, not low (I assumed low since it is described as an active high signal in she chip layout).  

So after some careful bodging a new pullup was expertly installed. But still no E clock out... What could it be? I started chasing ghosts in the board, stray capacitances, voltage levels. I bypassed all reset logic, removed all caps to all chips (one of them could be falty for all I knew), but still no E clock.  

I built a free running circuit on a bread board to test the processor (by setting the data lines to represent $12, the NOP instruction) and could emediately see a E clock and counting on the address lines. Good, now I knew that the processor was OK at least. So back to the board again.  

To rule out a faulty board (I had massacered it a bit in the hunt) I built prototype 2, but whitout anything that was not needed to make it free running.  

Did this work... Nope! Still no E clock. !"#%!#¤!"%  

I was now starting to questioning my own capability (I have only been tinkering with electronics and computers for 40 years) and considered to take up sheep herding instead.  

But I sat down at the table with my board again and looked over every pin on the processor for the fifty-eleventh time... And lo and behold, I had connected the ocillator to the wrong crystal pin! DOH! as Homer Simpsson would say! I quickly switched pins and E clock started ticking on prototype board #2. That was very nice to see that clock!!!  

I put the memories and the GALs back and tried that and got that running as well. I still had some issues with the WR/RD signals, but that is something I can fix in the GAL program.  

IT WORKS!!!  


