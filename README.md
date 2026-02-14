# AI-Driven Edge Monitoring and Compliance System

An embedded TinyML-based environmental sound classification system designed to detect policy-violating noise events in residential societies. The system performs real-time audio classification on-device and automatically generates structured logs and compliance alerts without cloud dependency.

---

## Overview

This project addresses the common issue of excessive noise in residential areas where residents often lack evidence to file formal complaints.

The system uses an ESP32 microcontroller with an INMP441 I2S microphone to:

* Classify environmental audio (party music, speech, construction, silence)
* Detect threshold-based violations
* Record audio evidence
* Generate timestamped logs
* Send structured email alerts to concerned authorities

All inference runs locally on the device using a TinyML model optimized for low memory and latency constraints.

---

## Key Features

* On-device real-time sound classification
* 90% classification accuracy
* 5ms inference latency
* 14KB optimized TinyML model
* 9.5KB peak RAM usage
* 63KB flash consumption
* Automated logging and evidence recording
* Threshold-based violation detection
* Email-based compliance reporting
* Fully offline inference (no cloud dependency)

---

## System Architecture

1. Audio Capture

   * INMP441 I2S microphone captures environmental sound
   * Raw waveform streamed to ESP32

2. Signal Processing

   * Feature extraction performed using Edge Impulse DSP pipeline
   * Audio transformed into ML-compatible feature vectors

3. On-Device Inference

   * TinyML model deployed on ESP32
   * Classifies sound into predefined categories

4. Violation Engine

   * If classified as "party music" beyond threshold duration
   * System triggers:

     * Audio recording
     * Log generation
     * Email alert dispatch

---

## Dataset

* 40,000+ custom-labeled audio waveform samples
* Categories:

  * Party Music
  * Talking
  * Construction
  * Silence
* Data preprocessed and mapped using Python
* Model trained and optimized via Edge Impulse

---

## Hardware Components

* ESP32 Microcontroller
* INMP441 I2S MEMS Microphone
* WiFi-enabled SMTP communication

---

## Software Stack

* Python (data preprocessing and dataset preparation)
* Edge Impulse (model training and TinyML optimization)
* Arduino (firmware development in C++)
* SMTP protocol for email alerts

---

## Performance Metrics

| Metric                  | Value           |
| ----------------------- | --------------- |
| Classification Accuracy | 90%             |
| Model Size              | 14KB            |
| Inference Latency       | 5ms             |
| Peak RAM Usage          | 9.5KB           |
| Flash Usage             | 63KB            |
| Dataset Size            | 40,000+ samples |

---

## Optimization Strategy

* Model quantization and pruning for reduced footprint
* Efficient feature extraction pipeline
* Memory-aware firmware design
* Threshold-based filtering to reduce false alerts

---

## Use Cases

* Residential society noise monitoring
* Automated compliance systems
* Smart building monitoring
* Edge AI for policy enforcement
* Low-power embedded ML applications

---

## Future Improvements

* Multi-device distributed monitoring
* Mobile dashboard for live tracking
* Integration with cloud analytics
* Adaptive threshold tuning
* Expanded sound class detection

---



