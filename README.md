OFDM-Based Wireless Communication System (MATLAB)

This repository contains a complete MATLAB implementation of a baseband OFDM communication system with AWGN and Rayleigh multipath fading channels. The project includes pilot-based channel estimation and two equalization techniques (ZF and MMSE), along with BER analysis and constellation visualization.

1. Overview

The goal of this project is to simulate a practical OFDM communication chain similar to those used in WiFi, LTE, and 5G systems. The system performs:

QPSK modulation

OFDM modulation using IFFT

Cyclic prefix insertion

AWGN and Rayleigh multipath fading

Pilot-based channel estimation

ZF and MMSE equalization

FFT-based demodulation

BER vs SNR performance evaluation

The simulation demonstrates how multipath affects OFDM and how equalization significantly improves performance.

2. System Architecture

Transmitter:

Bit generation

QPSK modulation

Pilot insertion

IFFT (OFDM modulation)

Cyclic prefix addition

Channel:

AWGN noise

Rayleigh multipath fading (4-tap tapped delay line)

Receiver:

Remove cyclic prefix

FFT

Extract pilots

Channel estimation (LS + interpolation)

Equalization (ZF / MMSE)

QPSK demodulation

BER calculation

3. Key Features

OFDM modulation/demodulation

Pilot-based LS channel estimation

Rayleigh multipath fading channel

Zero-Forcing and MMSE equalization

BER vs SNR curves

Constellation diagrams for AWGN, no-EQ, ZF, and MMSE

Fully parameterized MATLAB code

4. File Structure
/src
    tx_ofdm.m
    channel_awgn.m
    rx_ofdm_basic.m
    ofdm_pilots_multipath_updated.m
    ofdm_sim_sweep.m

/results
    ber_compare.png
    ber_compare.csv
    constellation_awgn_example.png
    constellation_noeq_example.png
    constellation_zf_example.png
    constellation_mmse_example.png

README.md
LICENSE


(Your actual structure may vary — adjust as needed.)

5. Parameters Used
Parameter	Value
Subcarriers (N)	64
Cyclic Prefix	16 samples
Modulation	QPSK
Pilot Spacing	Every 4th subcarrier
Channel	4-tap Rayleigh fading
Equalizers	ZF, MMSE
SNR Range	0 to 20 dB
OFDM Symbols per SNR	200
6. Running the Simulation

In MATLAB:

Place all .m files in the same directory

Set current folder to the project directory

Run:

ofdm_pilots_multipath_updated


Results will be saved in the folder:

ber_compare.png

ber_compare.csv

constellation images

7. Results Summary

AWGN channel achieves near-zero BER at moderate SNR.

Multipath without equalization performs poorly.

ZF equalization improves performance but amplifies noise at low SNR.

MMSE equalization gives the best performance across all SNR values.

Constellation plots clearly show distortion and correction.

8. Future Work

Potential improvements:

CFO and timing synchronization

LMMSE channel estimation

Forward error correction (LDPC, Turbo, Convolutional codes)

Adaptive modulation (QPSK, 16-QAM, 64-QAM)

MIMO-OFDM (2×2, 4×4)

FPGA/RTL implementation of OFDM blocks

SDR-based over-the-air transmission

9. License

This project is released under the MIT License.
See the LICENSE file for details.

