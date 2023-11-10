# Asteroid

## Introduction

- An open-source  toolkit for deep learning-based
audio source separation and speech enhancement, designed for
researchers and practitioners
- It follows the encoder-masker-decoder approach, and
provides various choices of filterbanks, masker networks, and
loss functions.

## Functionality

### Analysis and synthesis filterbanks

- free filters
- discrete Fourier transform (DFT) filters
- analytic free filters
- improved parameterized sinc filters
- the multi-phase Gammatone filterbank

### Loss functions — Permutation invariance
Supported loss functions 

- mean squared error
- scale-invariant signal-to-distortion ratio (SI-SDR)
- scale-dependent SDR
- signal-to-noise ratio (SNR)
- perceptual evaluation of speech quality (PESQ) and affinity loss for deep clustering 

### Masker network
Provides implementation of following masker networks:
- TasNet's LSTM
- Conv-Tasnet's temporal convolutional network
(with or without skip connections)
- DPRNN (Dual Path Recurrent Neural Network)
- Open-Unmix

# References:
https://arxiv.org/pdf/2005.04132.pdf