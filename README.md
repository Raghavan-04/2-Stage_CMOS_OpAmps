
## Project Title: Design and Analysis of 1-Stage and 2-Stage CMOS Op-Amps
Technology: gpdk180 (180nm) | Supply Voltage: 1.8V
### Introduction
This project explores the design, sizing, and simulation of high-performance Operational Amplifiers (Op-Amps). An Op-Amp is a high-gain differential amplifier used for signal amplification and analog processing. The repository provides a direct performance comparison between a Single-Stage Differential Pair and a Two-Stage Miller-Compensated Op-Amp.


### Design Specifications
The designs were optimized for different performance targets using a 1.8V power supply:

Parameter	1-Stage Target	2-Stage Target
Technology	gpdk180	gpdk180
Load Capacitance ($C_L$)	10 pF	2 pF
Gain	$\ge$ 40 dB	60 dB
Gain Bandwidth (GBW)	$\ge$ 5 MHz	30 MHz
Slew Rate (SR)	5 V/$\mu$sec	$\ge$ 42 V/$\mu$sec
### Design Methodology & Sizing
The sizing of MOSFETs follows a structured analytical approach. For the two-stage design, Miller Compensation and Pole-Splitting techniques were employed to maintain stability.

#### Key Design Equations
1.  Bias Current ($I_5$): Derived from the Slew Rate requirement: $I_5 = SR \cdot C_c$. 
2.  Transconductance ($g_m$): Defined by the GBW: $g_{m1,2} = GB \times C_c$. 
3.  Transistor Sizing ($W/L$): Calculated using the saturation current formula: $(\frac{W}{L}) = \frac{g_m^2}{2 I_D K'_n}$. 

### Simulation Results
The designs were verified using AC analysis and transient simulations.

Metric	Single-Stage Result	Two-Stage Result
Voltage Gain	40.8 dB	59.85 dB
Gain Bandwidth	4.69 MHz	30.3 MHz
Phase Margin	89.5°	47.253°
Slew Rate	5.32 V/$\mu$s	42.5 V/$\mu$s
CMRR	88.10 dB	96.64 dB
### Key Takeaways
*  High Gain vs. Stability: The two-stage design provides a significant boost in gain (nearly +20 dB) but requires careful compensation to avoid a low phase margin. 
*  Speed: The two-stage architecture is significantly faster, offering nearly 8x the Slew Rate of the single-stage design. 
*  Precision: The two-stage design is better suited for precision applications due to its higher CMRR and amplification. 

