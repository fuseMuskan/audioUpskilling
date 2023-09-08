# Audio Signal Processing Concepts

## Amplitude Envelope
- **Definition:** The amplitude envelope of an audio signal represents the variation in amplitude over time. It provides information about the signal's loudness changes.
- **Usage:** Useful for tasks like voice activity detection and sound classification.
  
## Root-mean-squared Energy
- **Definition:** Root-mean-squared energy is a measure of the signal's energy calculated as the square root of the mean of the squared amplitudes over a window of samples.
- **Usage:** It's often used for speech and audio feature extraction, as it characterizes the signal's overall energy content.

## Zero-Crossing Rate (ZCR)
- **Definition:** ZCR measures how quickly the signal changes polarity (crosses zero) within a frame. It's an indicator of the signal's noisiness or percussiveness.
- **Usage:** Valuable for tasks like speech and music analysis, particularly in distinguishing between voiced and unvoiced sounds.

## Short-Time Fourier Transform (STFT)
- **Definition:** STFT is a technique to analyze how the frequency content of a signal changes over time by applying the Fourier transform to small, overlapping windows of the signal.
- **Usage:** Essential for tasks like spectrogram generation and extracting time-varying spectral features.

## Mel-Scale
- **Definition:** The Mel scale is a perceptual scale of pitch that provides a better representation of human auditory perception than a linear frequency scale.
- **Usage:** Commonly used in audio processing, especially for tasks like speech recognition and audio compression.

## Mel-Frequency Cepstral Coefficients (MFCC)
- **Definition:** MFCCs are coefficients representing the short-term power spectrum of a sound signal, typically used as features in speech and audio analysis.
- **Usage:** Widely used in speech and audio processing for tasks such as speaker recognition, speech recognition, and music genre classification.

## Band Energy Ratio
- **Definition:** Band energy ratio calculates the ratio of energy within specific frequency bands of an audio signal. It can help identify the distribution of energy across frequency ranges.
- **Usage:** Useful in tasks like audio scene classification and music genre recognition.

## Spectral Centroid
- **Definition:** Spectral centroid is a measure of the center of mass of the spectrum of an audio signal. It indicates where the "center of gravity" of the spectral content lies.
- **Usage:** Valuable for tasks like timbre analysis, musical instrument classification, and speech processing.
