# NBSS

## Introduction

- **Neural Network:**
  - Introduction of SpatialNet, a neural network designed for multichannel joint speech tasks.
  - Focus on spatial information for speech separation, denoising, and dereverberation.

- **Architecture in STFT Domain:**
  - Performs end-to-end speech enhancement in the short-time Fourier transform (STFT) domain.
  - Composed of interleaved narrow-band and cross-band blocks.

- **Narrow-Band Blocks:**
  - Processes frequencies independently.
  - Utilizes a self-attention mechanism for spatial-feature-based speaker clustering.
  - Applies temporal convolutional layers for temporal smoothing and filtering.

- **Cross-Band Blocks:**
  - Processes frames independently.
  - Uses a full-band linear layer and frequency convolutional layers.
  - Learns correlations between all frequencies and adjacent frequencies.

- **Experimentation:**
  - Experiments conducted on various simulated and real datasets.
  - Results demonstrate:
    1. State-of-the-art performance on almost all tasks.
    2. Little susceptibility to the spectral generalization problem.
    3. Confirmation of speaker clustering through attention maps.

# References
* https://arxiv.org/pdf/2307.16516.pdf
* https://github.com/Audio-WestlakeU/NBSS