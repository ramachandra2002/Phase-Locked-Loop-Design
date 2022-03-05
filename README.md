# Phase Locked Loop Design using Skywater130
This repository contains the details about design of Phase locked loop using skywater 130nm node. This design was done as part of the workshop conducted by VSD.

![PLL-Workshop-Banner_efabless](https://user-images.githubusercontent.com/89923461/156775688-b91d4aad-f1fa-429f-a885-322b38c53e09.png)

# Day 1: PLL Theory and Lab Setup

# Introduction to PLL

# Day 2: PLL Labs and Post Layout Simulations

# Pre Layout Design and Simulations
The PreLayout Simulations are done using *ngspice* software. First we must create a *.spice* file, to write about the nodes and the components present in the design. And then to simulate type this command in the terminal,

```
ngspice <filename.cir>
```
## Phase Frequency Detector
The phase frequency detector circuit which we are going to simulate is,

![pfd-127782010-b21f76ed-6bed-4406-bfd0-2c5fca9838ac](https://user-images.githubusercontent.com/89923461/156877677-f6fb9085-c444-47a9-8a30-49558db0d413.jpeg)

The spice file for this corresponding circuit is,

![spice1_Picture1](https://user-images.githubusercontent.com/89923461/156877790-7f5079ec-c1e4-4565-b0bb-fde5499929fa.png)

After the `ngspice PD.cir` command, 

![after_Picture1](https://user-images.githubusercontent.com/89923461/156877792-c4556565-cfce-4e4b-8ad3-e9d28dc81fbf.png)

![wave_Picture1](https://user-images.githubusercontent.com/89923461/156877791-d5e7f439-322d-4971-8fdd-22526ffa18d6.png)

## Frequency Divider

The Frequency divider circuit which we are going to simulate is,

![fd_ckt127781480-b09756aa-a4ce-48e4-8164-4fad67cf1f7d](https://user-images.githubusercontent.com/89923461/156878013-75848c29-5416-4e0a-a19f-55122ca9503f.jpeg)

The spice file for this corresponding circuit is,

![sp_Picture1](https://user-images.githubusercontent.com/89923461/156878010-63434cb2-083f-43d0-8ed0-842e7a6da414.png)

After the `ngspice FD.cir` command, 

![wave_Picture1](https://user-images.githubusercontent.com/89923461/156878011-5fa267f0-16ad-4545-9c93-18935b4e44f6.png)

## Charge Pump

The Charge Pump circuit which we are going to simulate is,

![1cp_127782045-6a5b2df2-13fd-4456-9337-6b2af6604d05](https://user-images.githubusercontent.com/89923461/156878233-d100f4ce-3547-49d4-bad5-8e1e632cff15.jpeg)

The spice file for this corresponding circuit is,

![2sp_Picture1](https://user-images.githubusercontent.com/89923461/156878228-61b02379-3738-4c72-8b67-69c7c961bb9e.png)

After the `ngspice CP.cir` command,

![3sim_Picture1](https://user-images.githubusercontent.com/89923461/156878229-68e1e713-48a3-4c53-b757-2e36e72a1744.png)

![4sim_Picture1](https://user-images.githubusercontent.com/89923461/156878231-00157489-d031-4acc-a5c7-c090444637c2.png)

## Voltage Controlled Oscillator

The Voltage Controlled Oscillator circuit which we are going to simulate is,

![1ckt_127782614-ed6b8289-cf29-4cd9-bfe7-078176fe6c26](https://user-images.githubusercontent.com/89923461/156878480-70f66e20-4084-43eb-8eaa-7491c85c9f5a.jpeg)

The spice file for this corresponding circuit is,

![2sp_Picture1](https://user-images.githubusercontent.com/89923461/156878483-a396f05f-b4d1-4476-8359-8917601df69d.png)

After the `ngspice VCO.cir` command,

![3sim_Picture1](https://user-images.githubusercontent.com/89923461/156878474-f23d3464-6874-433a-9956-d0054403c202.png)

![4wav_Picture1](https://user-images.githubusercontent.com/89923461/156878479-2fc13160-57d6-4921-a9d7-ee5f83a5d685.png)


