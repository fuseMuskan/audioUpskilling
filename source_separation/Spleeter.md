# Spleeter

## Introduction:
* It is a music source separation tool.
* A tool that contains pre-trained models for:
    * vocals/accompaniment separation
    * 4 stems separation as in SiSec
    * 5 stems separation with an extra piano stem (vocals, bass, drums, piano and other)

## Implementation Details:
* `Architecture Used:` U-Net Architecture
* `No of Layers`: 12-Layer U-Nets (6 each for encoder and decoder)
* `Training Loss`: L1-Norm (between masked input mix spectrogram & source target spectrogram)

## Uses of the models:
* Vocal Lyrics Analysis from audio
* Music Transcription
* Singer Identification
* Multilabel Classification

## Performance Metrics Used:
* Signal to Distortion Ratio (SDR)
* Signal to Artifacts Ratio (SAR)
* Signal to Inference Ratio (SIR)
* Image to Spatial Distortion Ratio (ISR)