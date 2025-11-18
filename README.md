# Phase-Locked-Loop

## Design of a low power frequency synthesizer using Phase Locked Loops in 45nm and 180nm technology

## Tool used: Cadence Virtuoso
## Blocks designed:
### XOR gate as Phase Detector 
### Loop filter using 2nd order RC low pass circuit
### Ring oscillator as Voltage Controlled Oscillator 
### D Flip flop circuitry as frequency divider 
# PLL-Based Low Power Frequency Synthesizer

## Project Overview

This mini project presents the design, implementation, and analysis of a low-power Phase-Locked Loop (PLL) synthesizer suitable for modern high-performance and compact electronic applications. The architecture utilizes an XOR gate phase detector, a second-order low-pass filter, a ring oscillator as the voltage-controlled oscillator (VCO), and a frequency divider using a mod-N counter. The design is evaluated across both 45nm and 180nm CMOS processes, highlighting trade-offs in speed, power, and area efficiency.

---

## Abstract

A PLL system was implemented to achieve energy-efficient clock generation and frequency synthesis. The project evaluates key parameters like lock time, jitter, phase noise, and power. The 45nm design excels in speed and efficiency, apt for SoC and advanced communication systems, while 180nm provides robustness and cost-effectiveness for moderate-speed uses. Comparative analysis offers insights for choosing optimal technologies in different scenarios.

---

## Block Diagram 🗂️

The core PLL block consists of:

- **Phase Detector (XOR)**
- **Low-Pass Filter (2nd order RC)**
- **Voltage-Controlled Oscillator (Ring Oscillator)**
- **Frequency Divider (Mod-N Counter)**

> Add the original schematic/block diagram image here (`/assets/block_diagram.png`).

---

## Key Features

- **Low Power Design:** Optimized for minimal power consumption.
- **XOR-Based Phase Detector:** Simple and efficient phase comparison.
- **Second-Order RC Filter:** Effective noise suppression and stable loop dynamics.
- **Ring Oscillator VCO:** Broad tuning range, compact integration.
- **Frequency Divider (Mod-N Counter):** Robust digital frequency division.

---

## Methodology

### 1. Phase Detector
- XOR gate outputs voltage proportional to phase difference.
- 45nm node provides faster switching, reducing jitter and noise.

### 2. Low-Pass Filter
- Second-order RC filter with cutoff  
  \[
  f_c = \frac{1}{2\pi RC}
  \]
- Values used:  
  - \( R = 1.6\,k\Omega \)  
  - \( C = 10\,pF \)  
  - Cutoff ≈ 9.94 MHz  
- Designed for loop stability and reduced overshoot.

### 3. Voltage-Controlled Oscillator
- 5-stage ring oscillator.
- Inverter delay ≈ 100ps (45nm), \( R = 100\Omega \), \( C = 1.45pF \).
- Tuning range:
  - **45nm:** 10 MHz – 1 GHz  
  - **180nm:** Moderate range, higher power

### 4. Frequency Divider
- Implemented using mod-N counter and flip-flops.
- Ensures accurate frequency scaling and minimal propagation delay.

---

## Results and Comparative Analysis 📊

| Feature          | 45nm CMOS | 180nm CMOS |
|------------------|-----------|------------|
| Lock Time        | Faster    | Slower     |
| Jitter           | Lower     | Higher     |
| Power            | Lower     | Higher     |
| Area             | Smaller   | Larger     |
| Noise Robustness | Sensitive | Robust     |

---

## Conclusion 🚦

- **45nm PLL:** Best suited for high-performance applications such as SoCs and communications systems. Offers better efficiency and compactness, but more sensitive to noise and manufacturing variations.
- **180nm PLL:** Ideal for cost-efficient, reliable, and moderate-performance applications. Easier to design but consumes more power and area.

---

## References

1. B. Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill, 2001.  
2. R. E. Best, *Phase-Locked Loops Design, Simulation, and Applications*.  
3. S. Sun & T. H. Lee, "A second-order PLL design methodology", IEEE Circuits and Systems Magazine.  
4. Additional references from project report.

---

## Credits 👩‍🎓

- **Nandita Hosamani**  
- **Prajnya Shenoy**  
- **Pranathi R**  
- **Ramya Sheshadri**  
- **Guide:** *Archana H R, BMS College of Engineering*

---







#### Block diagram of Phase Locked Loop:
![PLL FINAL BLOCK DIAGRAM](https://github.com/user-attachments/assets/25f87119-2446-4adb-96b5-9532ed10733c)


## Phase detecctor using XOR gate:
![xor pd 180nm ckt](https://github.com/user-attachments/assets/aff643b6-14b8-4936-b1f4-f53c52011e11)

## Output using 45nm CMOS technology:
![45 nm pd ](https://github.com/user-attachments/assets/ea02b135-5731-483f-aa85-6a1d98bc9e04)

## Output using 180nm CMOS technology:
![180nm pd ](https://github.com/user-attachments/assets/bbdaf8e5-ebaa-4df5-9f34-ae94ed795e4e)

## Output using 2nd order filter in 45nm technology: 
![45nm filter op](https://github.com/user-attachments/assets/0ae04a19-4c1a-4efe-8243-f0deafa59ca3)


## 180nm:
![180nm filter op](https://github.com/user-attachments/assets/6846e0f4-090b-46fe-9850-34c5bca8c28c)


## Voltage contolled oscillator:
### 45nm:
<img width="1000" alt="VCO CKT 45NM" src="https://github.com/user-attachments/assets/51efad91-d42c-4243-ad80-db765cf5f2b2" />
![vco 45nm output](https://github.com/user-attachments/assets/355629b5-7b7e-40ae-b2c9-e77701701aca)



### 180nm:
![vco 180nm circuit](https://github.com/user-attachments/assets/54ed3527-15e8-4db4-b2d2-57dcbb3d7870)
![vco 180nm output](https://github.com/user-attachments/assets/c5121143-d077-4d0b-9172-164583412460)


## Frequency divider:





