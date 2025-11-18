# Phase-Locked-Loop
# Design of a low power frequency synthesizer using Phase Locked Loops in 45nm and 180nm technology

## Project Overview
This mini project presents the design, implementation, and analysis of a low-power Phase-Locked Loop (PLL) synthesizer suitable for modern high-performance and compact electronic applications. The architecture utilizes an XOR gate phase detector, a second-order low-pass filter, a ring oscillator as the voltage-controlled oscillator (VCO), and a frequency divider using a mod-N counter. The design is evaluated across both 45nm and 180nm CMOS processes, highlighting trade-offs in speed, power, and area efficiency.

---

## Abstract

A PLL system was implemented to achieve energy-efficient clock generation and frequency synthesis. The project evaluates key parameters like lock time, jitter, phase noise, and power. The 45nm design excels in speed and efficiency, apt for SoC and advanced communication systems, while 180nm provides robustness and cost-effectiveness for moderate-speed uses. Comparative analysis offers insights for choosing optimal technologies in different scenarios.

---

## Block Diagram:

The core PLL block consists of:

- **Phase Detector (XOR)**
- **Low-Pass Filter (2nd order RC)**
- **Voltage-Controlled Oscillator (Ring Oscillator)**
- **Frequency Divider (Mod-N Counter)**

#### Block diagram of Phase Locked Loop:
![PLL FINAL BLOCK DIAGRAM](https://github.com/user-attachments/assets/25f87119-2446-4adb-96b5-9532ed10733c)

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
-# PLL-Based Low Power Frequency Synthesizer

## Methodology

### 1. Low-Pass Filter (2nd Order RC)
**Cutoff frequency formula:**
fc = 1 / (2 * π * R * C)

**Values used:**
- R = 1.6 kΩ
- C = 10 pF

**Calculated cutoff:**

fc = 1 / (2 * π * 1.6k * 10p)  
fc ≈ 9.94 MHz

---

### 3. Ring Oscillator (VCO)

**Oscillation frequency formula:**

fosc = 1 / (2 * N * td)

Where:  
- N = number of inverter stages  
- td = delay of one inverter

**Given values:**
- N = 5  
- td ≈ 100 ps (45 nm)

**Frequency:**
fosc = 1 / (2 * 5 * 100ps)  
fosc = 1 / (1000ps)  
fosc = 1 GHz

---

### 4. Frequency Divider
- Implemented using mod-N counter and flip-flops.
- Ensures accurate frequency scaling and minimal propagation delay.
- **Output frequency:**
fout = fin / N

---

## Results and Comparative Analysis

| Feature          | 45nm CMOS | 180nm CMOS |
|------------------|-----------|------------|
| Lock Time        | Faster    | Slower     |
| Jitter           | Lower     | Higher     |
| Power            | Lower     | Higher     |
| Area             | Smaller   | Larger     |
| Noise Robustness | Sensitive | Robust     |

---

## 1.Phase detecctor using XOR gate:
- In a PLL, the XOR gate compares the phase of the reference and output signals, generating a voltage proportional to the phase difference.
- It thus gives a high output(error voltage) when the output frequency which is feedback to the phase detector is not the same as the reference frequency.
  
![xor pd 180nm ckt](https://github.com/user-attachments/assets/aff643b6-14b8-4936-b1f4-f53c52011e11)

## Output using 45nm CMOS technology:
![45 nm pd ](https://github.com/user-attachments/assets/ea02b135-5731-483f-aa85-6a1d98bc9e04)

## Output using 180nm CMOS technology:
![180nm pd ](https://github.com/user-attachments/assets/bbdaf8e5-ebaa-4df5-9f34-ae94ed795e4e)

### Inference: 
- The XOR-based phase detector showed a linear phase detection range of ±90°, with low 
power consumption.
- The output phase difference was converted into a voltage signal, 
exhibiting slight non-linearity near the range limits, which was effectively filtered by the lowpass filter.

## 2. 2nd order Low Pass Filter:
 - It ensures the PLL operates in a stable manner, without excessive overshoot, oscillations, or jitter.
 - The filter determines the PLL's loop bandwidth, which affects locking time, noise suppression, and the ability to track changes in the input signal.
   
## Output using 2nd order filter in 45nm technology: 
![45nm filter op](https://github.com/user-attachments/assets/0ae04a19-4c1a-4efe-8243-f0deafa59ca3)

## 180nm:
![180nm filter op](https://github.com/user-attachments/assets/6846e0f4-090b-46fe-9850-34c5bca8c28c)

### Inference:
- The second-order RC low-pass filter successfully suppressed high-frequency noise at the output of the phase detector.
- The chosen cutoff frequency provided a good balance between noise attenuation and settling time, ensuring that the PLL locked quickly and stably.

## 3.Voltage contolled oscillator:
- It consists of an odd number of inverters connected in a loop.
- The inverters create a feedback loop, generating an oscillating signal at a frequency determined by the delay of the inverters and the loop length.
- The oscillation frequency can be adjusted by changing the voltage applied to the inverters, making it suitable for use as a VCO.

### Output using 45nm tech:
<img width="1000" alt="VCO CKT 45NM" src="https://github.com/user-attachments/assets/51efad91-d42c-4243-ad80-db765cf5f2b2" />
![vco 45nm output](https://github.com/user-attachments/assets/355629b5-7b7e-40ae-b2c9-e77701701aca)

### Output using 180nm tech:
![vco 180nm circuit](https://github.com/user-attachments/assets/54ed3527-15e8-4db4-b2d2-57dcbb3d7870)
![vco 180nm output](https://github.com/user-attachments/assets/c5121143-d077-4d0b-9172-164583412460)

### Inference:
The ring oscillator-based VCO offered a tuning range from 10MHz to 1GHz with controlled biasing. 

## 4.Mod-n counter as frequency divider:
- Divides the frequency of the input signal by N. 
- The counter output toggles (changes state) once every N clock pulses.
- This toggling corresponds to a frequency that is 1/N of the input frequency.
  <img width="379" height="194" alt="image" src="https://github.com/user-attachments/assets/3a3cf856-62f8-4902-bea7-ba11a8340da4" />

  <img width="342" height="184" alt="image" src="https://github.com/user-attachments/assets/c121f203-e950-46c3-8451-675dc4f477b0" />

  <img width="374" height="272" alt="image" src="https://github.com/user-attachments/assets/952c6a71-e524-4cda-8d77-ad9b4ed188a0" />

  <img width="376" height="164" alt="image" src="https://github.com/user-attachments/assets/fd75e4dc-0c63-4a46-a716-be44b150900a" />





## Conclusion:

- **45nm PLL:** Best suited for high-performance applications such as SoCs and communications systems. Offers better efficiency and compactness, but more sensitive to noise and manufacturing variations.
- **180nm PLL:** Ideal for cost-efficient, reliable, and moderate-performance applications. Easier to design but consumes more power and area.

---

## References

1. B. Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill, 2001.  
2. R. E. Best, *Phase-Locked Loops Design, Simulation, and Applications*.  
3. S. Sun & T. H. Lee, "A second-order PLL design methodology", IEEE Circuits and Systems Magazine.  
4. Additional references from project report.

---

## Credits

- **Nandita Hosamani**  
- **Prajnya Shenoy**  
- **Pranathi R**  
- **Ramya Sheshadri**  
- **Guide:** *Archana H R, BMS College of Engineering*


