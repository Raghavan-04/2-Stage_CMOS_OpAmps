

# Design and Verification of 1-Stage and 2-Stage Operational Amplifiers

An analog IC design project comparing a Single-Stage Op-Amp and a Two-Stage Miller-Compensated Op-Amp using the **gpdk180 (180nm) technology node**.

## 🏫 Institutional Affiliation
* **College:** PSG College of Technology, Coimbatore 
* **Department:** Electronics and Communication Engineering / VLSI Design 
* **Batch:** Batch 14 

## 👥 Project Team
* **Mithun Hari** (22L232) 
* **Raghavan** (22L255) 
* **Vijhay Valliappan** (22L280) 
* **Thughilan** (22L284) 


---

## 📌 Project Overview
This project focuses on the complete design, transistor sizing, and simulation verification of two distinct Operational Amplifier architectures. The designs transition from foundational single-pole configurations to high-performance, stabilized multi-stage systems optimized for raw gain, speed, and noise rejection.

### 📐 Process Parameters Used
* **NMOS:** $V_{tn} = 0.49\text{ V}$, $K_{n}' = 325\text{ }\mu\text{A/V}^2$
* **PMOS:** $V_{tp} = -0.46\text{ V}$, $K_{p}' = 63\text{ }\mu\text{A/V}^2$

---

## 📊 Performance Matrix (Simulated vs. Compared)

| Performance Parameter | 1-Stage Op-Amp | 2-Stage Op-Amp |
| :--- | :---: | :---: |
| **DC Differential Gain ($A_d$)** | 40.80 dB | 59.85 dB |
| **Common Mode Gain ($A_c$)** | -47.30 dB | -36.79 dB |
| **CMRR** | 88.10 dB | 96.64 dB |
| **Gain Bandwidth (GBW)** | 4.68 MHz | 30.29 MHz |
| **Phase Margin (PM)** | ~89.5° | 47.25° |
| **Slew Rate (SR)** | 5.32 V/μs | 42.50 V/μs |

---

## 🛠️ Circuit Architectures & Sizing

### 1. Single-Stage Op-Amp
A single-pole architecture utilizing a dual-input balanced-output differential amplifier paired with current mirrors to guarantee high common-mode rejection.

* **Final Aspect Ratios:** 
  * Differential Input Pair ($M1, M2$): $W/L = 7$
  * Active Load Mirrors ($M3, M4$): $W/L = 15$
  * Tail Current Mirrors ($M5, M6$): $W/L = 13.67$
* **Schematic & Waveforms:**
  <p>
    <img src="1_stage_schematic.png" width="45%" />
    <img src="1_stage_waveforms.png" width="45%" />
  </p>

### 2. Two-Stage Op-Amp (Miller Compensated)
An advanced architecture splitting the voltage amplification across two stages to maximize gain, implementing **Miller Compensation ($C_c$)** and **Pole-Splitting** to isolate the dominant and non-dominant poles for high-frequency loop stability.

* **Final Aspect Ratios:**
  * $M1, M2 = 6$ | $M3, M4 = 8$ | $M5 = 124.56$ | $M6 = 31.14$ | $M7, M8 = 4$
* **Schematic & Waveforms:**
  <p>
    <img src="2_stage_schematic.png" width="45%" />
    <img src="2_stage_waveforms.png" width="45%" />
  </p>

---

## 💡 Key Engineering Insights & Trade-offs
1. **The Stability vs. Gain Trade-off:** The 1-stage design behaves as a highly stable, inherently safe single-pole system ($PM \approx 89.5^\circ$), but its open-loop gain is brick-walled at $40.8\text{ dB}$. Adding a second stage safely pushes the gain up by nearly $20\text{ dB}$ ($59.85\text{ dB}$) and vastly widens the operating bandwidth to $30.3\text{ MHz}$, though it demands careful compensation to stay stable ($PM = 47.25^\circ$).
2. **Transient Performance:** By optimizing the inner stage charging currents through Miller compensation network equations, the 2-stage design achieves a blistering **8x boost in Slew Rate** ($42.5\text{ V/}\mu\text{s}$) compared to the single-stage variant ($5.32\text{ V/}\mu\text{s}$).

## ⚙️ CAD Tools Used
* **Cadence Virtuoso** (Schematic Capture)
* **Spectre Simulation Platform** (AC & Transient Analysis)
