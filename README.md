# Phase Locked Loop Design using Skywater130
This repository contains the details about design of Phase locked loop using skywater 130nm node. This design was done as part of the workshop conducted by VSD.

![PLL-Workshop-Banner_efabless](https://user-images.githubusercontent.com/89923461/156775688-b91d4aad-f1fa-429f-a885-322b38c53e09.png)

# Day 1: PLL Theory and Lab Setup

# Introduction to PLL

# Day 2: PLL Labs and Post Layout Simulations

# Pre Layout Design and Simulations
The PreLayout Simulations are done using *ngspice* software. First we must create a *.spice* file, to write about the nodes and the components present in the design. And then to simulate type this command in the terminal,

```
ngspice <filename.sp>
```
## Phase Frequency Detector
The phase frequency detector circuit which we are going to simulate is,

![pfd-127782010-b21f76ed-6bed-4406-bfd0-2c5fca9838ac](https://user-images.githubusercontent.com/89923461/156877677-f6fb9085-c444-47a9-8a30-49558db0d413.jpeg)

The spice file for this corresponding circuit is,

![spice1_Picture1](https://user-images.githubusercontent.com/89923461/156877790-7f5079ec-c1e4-4565-b0bb-fde5499929fa.png)

After the `ngspice PD.cir` command, 

![wave_Picture1](https://user-images.githubusercontent.com/89923461/156877791-d5e7f439-322d-4971-8fdd-22526ffa18d6.png)

![after_Picture1](https://user-images.githubusercontent.com/89923461/156877792-c4556565-cfce-4e4b-8ad3-e9d28dc81fbf.png)



