[![DOI](https://zenodo.org/badge/984052758.svg)](https://doi.org/10.5281/zenodo.15424078)

# Vib2StressNet
**Direct Estimation of Fatigue Stress Spectra from Bridge Vibration Signals**

---

## 📖 Overview

**Vib2StressNet** is a deep learning framework for directly estimating **fatigue stress spectra** from **bridge vibration (acceleration) signals**.

Conventional fatigue assessment requires:
- Dense strain sensor networks
- Stress/strain reconstruction
- Rainflow cycle counting

This project proposes an **end-to-end approach** that bypasses intermediate steps and predicts stress spectra directly, enabling a more **efficient and scalable structural health monitoring solution**.

This repository accompanies the paper:  
*Direct estimation of fatigue stress spectra from bridge vibration signals using an attention-enhanced convolutional neural network* :contentReference[oaicite:0]{index=0}

---

## 🚀 Key Contributions

- **End-to-end learning**: Acceleration → Stress spectra
- **Attention-enhanced CNN architecture** for temporal feature modeling
- **Speed-aware modeling** using auxiliary scalar input
- **Improved accuracy** over sequence-to-sequence baselines (MSE reduced from ~59.8 to ~0.34)
- **Validated on real-world bridge data** across multiple structures
- **Reduced dependence on strain instrumentation**

---

## 🧠 Methodology

The proposed workflow consists of:

1. **Data Collection**
   - Multi-channel acceleration signals
   - Temporary strain measurements (for training only)

2. **Label Generation**
   - Convert strain → stress
   - Apply rainflow counting to obtain stress spectra

3. **Model Training**
   - Input: acceleration signals (+ optional train speed)
   - Output: stress cycle counts across stress ranges

4. **Deployment**
   - Remove strain sensors
   - Predict stress spectra directly from vibration data

---

## 🏗️ Model Architecture

Vib2StressNet integrates:

- **1D Convolutional Neural Networks (CNNs)**  
  Capture local temporal and cross-sensor features

- **Residual Connections**  
  Improve training stability and preserve signal information

- **Multi-head Self-Attention**  
  Learn long-range temporal dependencies

- **Speed Embedding Module**  
  Incorporates train speed to account for resonance effects

The model outputs a **fixed-length vector of stress cycle counts**.

---

## 📊 Results

- Demonstrated strong generalization across **three railway bridges**
- Significant improvement in prediction accuracy:
  - MSE reduced from ~59.8 (baseline) to ~0.34
- Incorporating train speed improves performance by up to **~80%**
- Robust under:
  - Variable speeds
  - Dynamic loading
  - Resonance conditions

---

---

## ⚙️ Installation

```bash
git clone https://github.com/Kevinsvip888/Vib2StressNet.git
cd Vib2StressNet

pip install -r requirements.txt

## Citation
@article{meng2026vib2stressnet,
  title={Direct estimation of fatigue stress spectra from bridge vibration signals using an attention-enhanced convolutional neural network},
  author={Meng, Bo-wen and Bayane, Imane and Leander, John},
  journal={Engineering Structures},
  year={2026}
}

