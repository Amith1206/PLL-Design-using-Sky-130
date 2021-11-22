# PLL-Design-using-Sky-130
Phase Locked Loop(PLL) IC Design using Open-Source PDK's by Google-Skywater | VSD-IAT Workshop

## Introduction to PLL(Phase Locked Loop)

### What is PLL?
In simple terms,A phase-locked loop is a closed-loop feedback control circuit that's both frequency and phase sensitive.It is an electronic circuit with a voltage-driven oscillator that constantly adjusts to match the frequency of an input signal.It can also be used to generate a signal with a frequency that is multiplied by a fixed factor compared to the frequency of a reference signal.

### Why PLL?

**End Goal: To get precise clock signal without frequency or phase noise**
>Clock Signal can be generated using Voltage Controlled Oscillator(VCO) or Quartz Crystal

| Quartz Crystal|      VCO      |
| ------------- | ------------- |
| Can give signal with pure spectrum(single frequency)  | Presence of phase noise  |
| Not flexible | Flexible(can generate signals with flexible frequencies )  |

*The purpose of PLL is to make VCO mimic(same or multiple of ref freq) spectral purity of Quartz at the same time maintaing flexibility.*
<br>

## Block Diagram of PLL
[![vsd1.png](https://i.postimg.cc/zf1pkYcW/vsd1.png)](https://postimg.cc/qNj8kS0M)
