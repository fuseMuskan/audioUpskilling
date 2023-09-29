# Importance of phase
> Phase can be defined as the measure of the relative position of the waveform in a signal. It is measured in terms of angles (degrees, or radians).
> With phase information, we can estimate how a human ears percieve the sound in terms of timing and tone.
> Phase shift plays a vital role in determining the signal quality, whether it is broadcast, received, or transmitted.


# Summary of Model Based STFT phase recovery for audio source separation
* Link :https://hal.science/hal-01718718v1/document

# Abstract

* For audio source seperation, the most common methods follows the same method of estimating the magnitude of the Time-Frequency representation of each source and then use Wiener Filtering approach which use the phase from the original mixture.
* This paper introduces a iterative approach for soruce seperation.
* Many music events are partially composed of slowly varyoing sinusioids and the STFT phase increment of those frequency components take specific form. It allows phase recovery by an unwrapping technique over the estimation of short-term frequency.

# Introduction to Phase Unwrapping Algorithm
* It is suitable for variety of pitched music signals, such as piano or guitar sounds.
* Research has not been done on percussive sounds (noise like sounds and usually stems from instrument onsets like the hit on drum or from consonants in speech).
* This technique assumes that the magnitude spectrograms of the sources are estimated beforehand (using a NMF) and thus tackles only the phase recovert phase.
* It also assumes that there is at most one active sinusoid per frequency channel and per source.

# THE PHASE UNWRAPPING ALGORITHM
## A. Sinusoidal modeling
> It gives the relationship between two successive time frames.
## B. Mixtures of sinusoids.
> 