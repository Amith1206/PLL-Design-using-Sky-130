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

![Alt Text](vsd1.PNG)

## Components in detail

### 1. Phase Frequency Detector(PFD)

PFD Circuit is used to compare the input reference and output feedback signals to generate Up and Down signals depending on whether feedback signal leads or lags compared to reference signal.
***
#### **State Diagram**
![Alt Text](SD_PFD.jpeg)
***
#### **Circuit**
![Alt Text](pfd_ckt.png)
***
#### **Drawback**
When the phase difference between reference signal and feedback signal is very very small, the PFD circuit does not detect as Up/Down signals are not given enough time to toggle completely. This condition is called Dead Zone.Hence more precise circuit should be designed.


### 2.Charge Pump
![Alt Text](chargepump.PNG)

Charge Pump converts the digital input to a analog signal which is used by Voltage Controlled Oscillator(VCO) circuit. Charge Pump can ge designed using current steering circuit.

#### Working
If the Up signal is 1, the current flows from Vdd to output capacitor and charges it.<br>
If Down signal is 1, the current flows from output capacitor to Ground and discharges the Capacitor.<br>
The output of the charge pump depends on the average time of Up being 1 and Down being 1. If the average time with Up being 1 is more, output voltage increases and the voltage across capacitor decreases in other case.<br>

But there can be leakage current even if both Up and Down are 0.This leakage current can impact the output signal and inturn the performance of VCO. Moreover, there can be frequency fluctuations at the output of the Charge Pump and this can be taken care with the help of a Low Pass Filter (LPF) at the output.

Charge Pump Circuit with LPF at the output
![Alt Text](chargepump2.PNG)
