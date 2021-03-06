---
title: "SoC on FPGA - Part One: Overview"
publishDate: 2020-04-22 09:19:06 +0800
date: 2020-04-22 09:00:25 +0800
categories: FPGA SoC
position: blog
---

General introduction to FPGA and SoC.

---

<div id="toc"></div>

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="398" height="52" src="//music.163.com/outchain/player?type=2&id=1316412346&auto=1&height=32"></iframe>
A decent song for you.

FPGA, short for Field-Programmable Gate Array, and SoC, short for System on Chip are recently always brought to the media for its widely appilication. This article will illustrate briefly about what is SoC and what is FPGA.

## System on Chip (SoC)

Different from Central Process Unit (CPU) or Graphic Process Unit (GPU), SoC is a type of core that contains everything a programmer would need to programme on it. What does this mean? Take Jack, a programmer as example. Jack want to assemble a computer. What does he need? An Intel Core® i9, Titan® X Graphic Card, Samsung® DDR4 Memory and EVO® 970 Solid State Drive. Also, he will need a motherboard to supply power and cooling CPU, GPU and other stuffs. Also a AC-DC converter is required. After that, he will need to install an operating system, i.e. Ubuntu or Windows on the machine. To programme on the computer, the programming environment is also required. After all that, he could finally run some programs on this newly built computer.

What about Bob, a SoC engineer? He would just need to buy an Arduino and a AC-DC converter for power supply.

What SoC different from CPU is clear, that SoC is actually a fully prepared system for anyone to use, it contains Algrithom and Logic Unit(ALU) working as CPU, Static Random-Access Memory(SRAM), Clock Source, Flash, Power Control Unit(PWC), etc. Engineer could directly write programmes into its `Flash` and it will read programme from it to `Electrically-Erasable Programmable Read-Only Memory (EEPROM)` then operate automatically. Because all we need to programme are in the SoC the tiny little chip.
![ArduinoUnoStructure](https://s1.ax1x.com/2020/04/22/JNnCh4.png)
*Figure 1 Arduino Uno Structure*

## Field-Programmable Gate Array (FPGA)

FPGA is quite different from what we have talked above, it is a totally "Free" stuff. It is a chip contains millions of gates. And what is gate? Gate is refered to Logic Gate, i.e. XOR(exclusive OR) gate and AND gate. With the basic logic gates, we could make thousands of arrays and create the digital devices in the Text Book of Digital Circuits. For example, a simple D-Flip Flop(DFF) unit is implemented by 4 NAND gate and one Inverter. Furthermore, a shift register could be implemented by several DFF.
![DFF](https://www.electronicshub.org/wp-content/uploads/2015/05/4.D-Logic-Diagram.jpg)
*Figure 2 D-Flip Flop* From *electronic Hub*

Since stuffs in a SoC are all digital except for AC-DC converter, they could be implemented by the FPGA and thus the FPGA could be used as a simple SoC. That is what FPGA is always used for, the early stage verifidication of ASIC.
