[![DOI](https://zenodo.org/badge/984052758.svg)](https://doi.org/10.5281/zenodo.15424078)
# Vib2strssNet

# Vib2StressNet
**Direct Estimation of Fatigue Stress Spectra from Bridge Vibration Signals**

---

## Overview
Vib2StressNet is a deep learning framework that predicts **fatigue stress spectra directly from bridge vibration (acceleration) signals**, eliminating the need for intermediate stress/strain reconstruction and rainflow counting.

The model combines **convolutional neural networks (CNNs)** with **multi-head self-attention**, and incorporates **train speed as an auxiliary input** to improve accuracy under dynamic and resonance conditions.

📄 Based on: *Direct estimation of fatigue stress spectra from bridge vibration signals using an attention-enhanced convolutional neural network*

---

## Key Contributions
- End-to-end mapping: **acceleration → stress spectra**
- Attention-enhanced CNN for temporal feature learning  
- Integration of **train speed** for dynamic adaptation  
- Significant error reduction (MSE ↓ from ~59.8 to ~0.34)  
- Validated on multiple real-world railway bridges  

---

## Method
1. Collect acceleration signals (and temporary strain data for training)  
2. Generate stress spectra via rainflow counting  
3. Train Vib2StressNet  
4. Deploy using **acceleration-only inputs**  

---

## Installation
```bash
git clone https://github.com/Kevinsvip888/Vib2StressNet.git
cd Vib2StressNet
pip install -r requirements.txt
