# **Constraint-Based PID Tuning with Dynamic Reference Adjustment**  

This repository contains the code used in the study:  
**"Constraint-Based PID Tuning with Dynamic Reference Adjustment for Improved Patient Safety During Automated General Anesthesia"**  
by **Mohamad Ajami, Mirko Fiacchini, and Thao Dang**.  

If you have any questions, feel free to contact me. If you use this code for research purposes, please cite our paper.

---

## **Overview**  

This repository provides the necessary codes and dataset for simulation. The dataset is included, eliminating the need for users to generate a new one. The code is implemented in **Python 3.10**.

---

## **PID Tuning Approaches**  

### **1. PID Tuner A (Constraint-Based PID with Dynamic Reference Adjustment)**  
This approach tunes a **constraint-based PID controller** with dynamic reference adjustment.  

- The **induction phase** is tuned independently, and the resulting parameters are then used for tuning the **maintenance phase**.
- **Important Notes**:
  - The tuning results may vary between runs, as the optimization process is non-deterministic (*applies for tuners A and B*).
  - In some cases, the tuner may exaggerate the value of the **derivative time constant** during the induction phase. This can slow down convergence to prevent undershoot. If necessary, manual fine-tuning of the **derivative time constant** may be required for improved convergence.
  - Given the complexity of this method, multiple candidate PID parameters can be extracted, allowing users to choose the ones that best meet their objectives.
  - The parameters provided in this study were **not modified** post-tuning. They were selected directly from the tuner as they exhibited the best performance in our analysis.

---

### **2. PID Tuner B (Standard PID)**  
This method tunes a **standard PID controller** by minimizing the **Integral Absolute Error (IAE)**.  

- The induction and maintenance phase parameters are tuned **simultaneously** to achieve the lowest possible IAE.
- **Key Features**:
  - Since the optimization objective is simpler, no additional manual adjustments are required.
  - Users can still test different candidate PID parameters from the tuner and select the ones that best meet their objectives.
  - The parameters used in the study were the ones that achieved the **lowest IAE**.

---

### **3. Comparison**  
This script provides a detailed **performance comparison** between the two controllers based on the evaluation metrics outlined in the paper.

---

# License
GNU General Public License v3.0

# Project status
In review

# Author
Mohamad Ajami
