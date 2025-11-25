
---

# 📡 **OFDM Communication System – MATLAB Implementation**

**Author:** Adeetya (Aditya Solanke)
**Project Type:** DSP + Wireless Communication + MATLAB
**Status:** **Completed (Basic)** — Advanced features coming soon

---

## 🚀 **Project Overview**

This project implements a complete **baseband OFDM (Orthogonal Frequency Division Multiplexing)** communication link in MATLAB, including:

* Bit generation
* QPSK modulation
* OFDM modulation using IFFT
* Cyclic prefix insertion
* AWGN channel
* OFDM demodulation via FFT
* QPSK demodulation
* Bit Error Rate (BER) calculation
* BER vs SNR performance curve

This is a clean, modular MATLAB implementation that follows the actual structure used in modern systems like WiFi (802.11), LTE, and 5G OFDM.

---

## 🧩 **Project Structure**

Your folder contains:

```
📁 Project Folder
 ├── tx_ofdm.m             (OFDM Transmitter)
 ├── channel_awgn.m        (AWGN Channel Model)
 ├── rx_ofdm_basic.m       (Basic OFDM Receiver)
 ├── ofdm_sim_sweep.m      (BER vs SNR Simulation)
 ├── tx_data.mat           (Saved transmit data)
 ├── rx_data.mat           (Saved received data)
 ├── tx_time.png           (Time-domain TX waveform)
 ├── rx_time.png           (AWGN-corrupted RX waveform)
 ├── constellation.png     (QPSK constellation after RX)
 ├── ber_vs_snr.png        (BER vs SNR performance plot)
 ├── ber_vs_snr.csv        (Raw numeric results)
 └── README.md             (Project documentation)
```

---

## 🔧 **How the System Works**

### **1️⃣ Transmitter (tx_ofdm.m)**

* Generates random binary bits
* Groups bits into QPSK symbol indices
* Maps symbols using `pskmod`
* Applies IFFT → time-domain OFDM symbol
* Adds cyclic prefix
* Saves `tx_data.mat` + `tx_time.png`

---

### **2️⃣ Channel (channel_awgn.m)**

* Adds AWGN noise at a chosen SNR
* Saves `rx_data.mat` + `rx_time.png`

---

### **3️⃣ Receiver (rx_ofdm_basic.m)**

* Removes cyclic prefix
* Applies FFT
* QPSK demodulates using `pskdemod`
* Reconstructs bits
* Compares TX vs RX → computes BER
* Saves `constellation.png`

---

### **4️⃣ BER vs SNR Sweep (ofdm_sim_sweep.m)**

* Runs 200 OFDM symbols across SNRs 0 to 20 dB
* Calculates BER for each SNR
* Saves:

  * `ber_vs_snr.png`
  * `ber_vs_snr.csv`

---

## 📊 **Results**

### **🟦 BER Performance (QPSK-OFDM)**

See `ber_vs_snr.png` for the curve.

Typical result:

* High BER at 0 dB
* Error floor drops rapidly as SNR increases
* At 12–15 dB → BER reaches ~0

---

## 🎯 **Key Learnings**

By completing this project, you demonstrate knowledge of:

✔ Digital modulation (QPSK)
✔ OFDM baseband processing
✔ FFT/IFFT operations
✔ Cyclic prefix usage
✔ AWGN channel simulation
✔ Bit error rate evaluation
✔ MATLAB signal processing
✔ DSP system-level thinking

This aligns strongly with roles in:

* DSP Engineering
* Wireless Communications
* FPGA/RTL + Communication Systems
* Embedded Communication Firmware

---

## 🔥 **Planned Advanced Features (Coming Soon)**

### **Phase 2 — DSP Enhancements**

* Pilot subcarriers
* Channel estimation (LS / MMSE)
* Zero-Forcing equalizer
* MMSE equalizer

### **Phase 3 — Wireless System Reality**

* Multipath fading channel (Rayleigh, tapped delay line)
* BER comparison: AWGN vs fading vs equalized
* Synchronization (optional)

### **Phase 4 — Communication Engineering Skills**

* LDPC / convolutional coding (FEC)
* Frequency offset estimation
* Fixed-point OFDM (FPGA ready)
* Mapping some blocks to SystemVerilog

---

## 🛠 **How to Run**

Open MATLAB → Change current folder to project folder → Run:

1. `tx_ofdm.m`
2. `channel_awgn.m`
3. `rx_ofdm_basic.m`
4. `ofdm_sim_sweep.m`

All generated figures & data will appear in the same folder.

---

## 📎 **Notes**

* The system is fully parameterized (N, cp, M, numSymbols, SNR list).
* You can easily extend this into a research paper–style project.
* Perfect for GitHub, LinkedIn, and resume portfolio.

---
