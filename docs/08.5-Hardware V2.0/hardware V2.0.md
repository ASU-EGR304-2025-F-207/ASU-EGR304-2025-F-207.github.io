--- 
title: Hardware V2.0
tags:
- tag1
- tag2
---


The current hardware design works, but several changes could make the system more reliable and easier to maintain. The biggest improvement would be separating the design into two PCBs. Even though the schematic shows the sensors near each other, the motion sensor and depth sensor must be placed in completely different locations inside the trash can. Using a single PCB forces long wire runs, which can introduce electrical noise, complicate installation, and increase the risk of wires bending or breaking over time. Adding a dedicated “lid PCB” for the motion sensor and a separate “bin PCB” for the depth sensor would shorten wiring, reduce noise, and simplify assembly.

By giving each sensor its own board and its own channel, the microcontroller no longer has to manage overlapping readings or deal with interference caused by long wires. This reduces the chance of inaccurate sensor values, unstable analog readings, or accidental triggering when switching channels. With cleaner, isolated signals, the software can rely on simple ADC reads and basic thresholds without additional filtering or compensation. This makes the code easier to write, easier to debug, and far more stable during normal operation.
