# Phase Locked Loop Design using Skywater130
This repository contains the details about design of Phase locked loop using skywater 130nm node. This design was done as part of the workshop conducted by VSD.

![PLL-Workshop-Banner_efabless](https://user-images.githubusercontent.com/89923461/156775688-b91d4aad-f1fa-429f-a885-322b38c53e09.png)

# Day 1: PLL Theory and Lab Setup

# Introduction to PLL

The Phase Locked Loop is a circuit which can be clock signal generator without noise and generate a frequency of our choice. One of the main purpose of the PLL is to generate a signal with *pure spectrum* without other frequency noises. The main components of a basic PLL are Voltage Controlled Oscillator, Phase Frequency Detector, Charge Pump, Low pass filter, frequency divider.

![pll_photo_2022-03-05_17-17-22](https://user-images.githubusercontent.com/89923461/156881676-3c678632-b67d-4e2d-9c45-9f76994d2bcf.jpg)

## Phase Frequency Detector

The Phase Frequency Detector is a circuit whch can measure the phase difference between the two signals: input and reference signals. Initially, XOR was in the discussion for a phase detector from the signals. But the problem in using XOR as a phase frequency detector is that it cannot tell the difference between lagging and leading. The design of the phase detector is using two D Flip flops along with AND gate for detecting using the UP and DOWN signals. 

![pfd_photo_2022-03-05_19-01-42](https://user-images.githubusercontent.com/89923461/156885412-a51a223c-c82b-4b88-9692-354735e60b2a.jpg)

## Charge Pump

Charge Pump is a circuit that uses capacitors for energetic charge storage to raise and lower voltage. This circuit incorporates current steering circuits. Based on the given up or down signal, a current steering circuit steers or directs the current flow from the Vdd to the output or from the output to the ground. If the up signal is active, current travels from the Vdd to the output capacitor, charging it. The voltage at the CP output is raised as a result. When the down signal is activated, current flows from the output capacitor to ground, discharging the output. The voltage at the CP output is reduced as a result.

![cp_photo_2022-03-05_19-01-48](https://user-images.githubusercontent.com/89923461/156885426-ac49ed49-8ac1-4e48-9c0e-c62b7aea1ced.jpg)


## Voltage Controlled Oscillator

A Ring Oscillator is a circuit which contains a series of odd number of inverters. The frequency of oscillator depends upon the delay and charging capacity of the capacitance in the mos transistors. So, if the current is very high, the output may be charged more quickly. We can change the frequency of the ring oscillator by starving it of current.

## Frequency Divider

Frequency Divider is the circuit that produces an output that is the clock input divided by the specified value. The design of frequency divider contains a toggle D flip flop is half the frequency of the input signal. 

# Tools Used

- Ngspice: *for simulation of spice files*
- Magic: *for creating layouts for circuits*

# Specifications

- _Corner_ - TT
- _Supply_ - 1.8V
- _Room Temperature_
- _Input_ Fmin = 5MHz and Fmax = 12.5MHz
- _Multiplier_ - 8x
- _Jitter_ (RMS) <~ 20ns
- _Duty Cycle_ - 50%


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

## PLL using sub circuits

PLL design using the separate sub circuit's spice files,

![1sp_Picture1](https://user-images.githubusercontent.com/89923461/156878832-8457903e-1e59-4bdc-bfc6-1ee1a01e7c94.png)

After the `ngspice PLL_PreLay.cir` command,

![2sim_Picture1](https://user-images.githubusercontent.com/89923461/156878898-e19fc58e-7321-4e07-be47-ab3a785cea2e.png)

![2_127783355-32111d1c-00c2-4697-a09f-596713cf9852](https://user-images.githubusercontent.com/89923461/156878830-1c538091-8378-4330-af14-072391bc03a6.jpeg)


# Layout Design
The Layout Design for the sub circuits are done *magic* tool. The invoke the magic tool for new design, the command to type is,

```
magic -T <technology_file_name.tech> <layout.mag>
```

## Frequency Divider

By typing the command `magic -T sky130A.tech FD.mag`, we can open the layout of the circuit,

![Picture1](https://user-images.githubusercontent.com/89923461/156879510-ab278910-443a-413b-bee8-ace19e49f517.png)

## Phase Frequency Detector

By typing the command `magic -T sky130A.tech PFD.mag`, we can open the layout of the circuit,

![1_Picture2](https://user-images.githubusercontent.com/89923461/156879604-aa5c48cb-048d-4cb3-9ffa-c5cb9cfa8228.png)

![2_Picture2](https://user-images.githubusercontent.com/89923461/156879601-45ff9ab9-76b2-450f-98db-1894277f3a8d.png)

##  Charge Pump

By typing the command `magic -T sky130A.tech CP.mag`, we can open the layout of the circuit,

![1_Picture2](https://user-images.githubusercontent.com/89923461/156879649-39687d85-85b0-49b8-aed5-1b53c7bae09a.png)

![2_Picture2](https://user-images.githubusercontent.com/89923461/156879652-2bf43f52-decd-4b8c-a006-20306c896b66.png)

## Voltage Controlled Oscillator

By typing the command `magic -T sky130A.tech VCO.mag`, we can open the layout of the circuit,

![1_Picture2](https://user-images.githubusercontent.com/89923461/156879695-77ab69d9-dc65-4078-826d-1afea8c48981.png)

![2_Picture2](https://user-images.githubusercontent.com/89923461/156879696-8ab73d68-22af-4fe7-93f0-1a59971aacd1.png)

##  MUX

By typing the command `magic -T sky130A.tech MUX.mag`, we can open the layout of the circuit,

![Picture2](https://user-images.githubusercontent.com/89923461/156879975-e939df7f-095a-4e79-8227-b6786eba131f.png)

## PLL

 Once the sub circuits layouts are finished, we have to create a new layout and place the sub circuit layout using ` File > Place Instance`
 
 ![1_127783571-8c9939d1-c883-4e21-a04e-97d139257e1e](https://user-images.githubusercontent.com/89923461/156879939-59345484-3677-4521-9c32-c984e8593c05.jpeg)

# Parasitics and Post-Layout Simulation

Once the layouts of induvidual circuits are over, we need to extract the effect of capcitance in the circuit which is called as parasitics extraction. To extract the parasitics of the layout, we need to use the magic tool command

```
ext2spice
```
![1_Picture3](https://user-images.githubusercontent.com/89923461/156880821-0e40c9b3-7b0d-4397-9f91-740b81615094.png)

![2_Picture3](https://user-images.githubusercontent.com/89923461/156880822-208ee07d-6323-4823-b92c-4e687b66a281.png)

## Post-Layout Simulation

Once we get the the corresponding spice file from the PFD circuit's layout, we need the simulate and the check the output for the same.

```
ngspice PFD_PostLay.cir
```
![3_Picture3](https://user-images.githubusercontent.com/89923461/156880880-4c412d2a-1726-4de1-9b4e-84b0a37d99ef.png)

![4_Picture3](https://user-images.githubusercontent.com/89923461/156880881-4fe3a1c0-e38d-4c8d-a0e7-955c99fc02b6.png)

# Tapeout

GDSII file is regarded the final format for manufacturing, the IC designed cannot be provided in that format. The design must be "readied" for manufacture which is called as the tapeout. This preparation would include any addition that aids in connecting the wafer to the outside world. This might involve the addition of I/O ports, UARTs, and other peripherals. The below image shows what a Caravel SoC is,

![1_127822463-cd54b92b-b178-4f99-913d-33ef7c995c53](https://user-images.githubusercontent.com/89923461/156881172-e01536c0-2741-4ee8-8447-a3586717faa1.jpeg)

Inside the Caravel's design, our design an be placed using the magic tool. Finally, the inputs and outputs are connected to the carvel template design using the magic tool.

# Author

Ramachandra T, B.E in Electronics and Communication Engineering at Madras Institute of Technology, Anna University

# Acknowledgement

1. Kunal Ghosh, VSD Corp.
2. Lakshmi, MS ECE, Georgia Tech






