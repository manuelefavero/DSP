# Short Sound Recognition Through Frequency Response Analysis

## Introduction

This project investigates how **smartphone microphone frequency response** affects the recognition of **TIS (Transmission of Information Sound) codes**. TIScodes are short 5-second sound messages designed to **encode and transmit information through audio**, similar to QR codes but without requiring a camera. 

A key challenge in real-world applications is that **microphone characteristics vary significantly** across different smartphone models, potentially altering the captured TIScodes. This project aims to analyze these variations through **anechoic chamber experiments** and evaluate their impact on TIScode recognition using a **frequency peaks analysis method**.

## Experimental Setup: Anechoic Chamber Measurements

To measure how different smartphones capture audio signals, we conducted controlled experiments in an **anechoic chamber**, ensuring minimal environmental noise interference.

### 1. Frequency Response Measurement
- A **10-second frequency sweep (20Hz - 20kHz)** was played and recorded by **seven smartphones**:
  - OnePlus 8T, iPhone 13, Samsung Galaxy A54, Honor 9X, Motorola Moto E7, Realme 9 Pro, Xiaomi Redmi A03.
- The **frequency response** of each smartphone's microphone was calculated by comparing the original signal with the recorded one.
- The response was analyzed in **Linear, Logarithmic, and Mel scales** to observe how different frequency bands were affected.

### 2. Inverse Filtering for Signal Correction
- An **inverse filter** was designed to compensate for the frequency distortions introduced by each microphone.
- The effectiveness of the correction was measured using **Signal-to-Noise Ratio (SNR)** and **Mean Squared Error (MSE)**.

## Frequency Peaks Analysis for TIScode Recognition

Once the microphone characteristics were measured, we evaluated how well **TIScodes** could be recognized under real-world conditions:

1. **TIScodes Dataset**: 100 unique sound sequences were generated using MusicGen.
2. **Noise Simulation**: TIScodes were overlaid with different background noises:
   - **Hospital Noise Dataset** (e.g., conversations, medical equipment, ambient sounds).
   - **General Ambient Noise Dataset** (e.g., wind, rain, white noise, construction sounds).
3. **Recognition System**: 
   - The most prominent **frequency peaks** of each TIScode were extracted and compared with a database.
   - The recognition test was performed under different **TIScode attenuation levels** (0 dB, -3 dB, -6 dB, -9 dB).

## Results and Findings

- **Microphone Frequency Response Variations**:
  - The **Linear, Logarithmic, and Mel** scale responses showed **significant differences** among devices.
  - Applying the frequency response of one scale to another **did not yield satisfactory filtering results**.
  - Even among widely used commercial smartphones, **microphone response differences impact recognition accuracy**.

- **Recognition Performance**:
  - Without noise correction, **67% of TIScodes were correctly recognized** when noise and TIScode were at equal intensity.
  - With **6 dB noise attenuation**, the recognition rate improved to **93.2%**.
  - The system significantly outperformed the **existing TIScode recognition method**, which only achieved **11% accuracy** in real-world tests.

## Future Work

- Expanding the dataset to **higher-end smartphones** to evaluate if better microphone quality improves results.
- Refining the **inverse filtering techniques** to provide more accurate frequency response compensation.
- Investigating **adaptive noise filtering methods** to enhance recognition in challenging environments.

## Authors

- **Manuele Favero**
- **Lavinia Verzotto**
