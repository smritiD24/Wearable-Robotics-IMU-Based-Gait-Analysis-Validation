# Dual-Shank IMU-Based Gait Analysis & Validation

**MSc Thesis Project — Human-Centred Robotics Lab, IIT Gandhinagar**

---

## Overview

This repository documents the gait analysis pipeline developed 
as part of my MSc thesis. The study proposes and validates a 
dual shank-mounted IMU system for estimating spatial and temporal 
gait parameters, benchmarked against Vicon motion capture 
(gold standard) across 10 healthy subjects during treadmill 
and overground walking.

> ⚠️ **This study is currently under preparation for publication. 
> Code and data will be made available upon acceptance.**

---

## Research Summary

- Dual IMU system (shank-mounted, bilateral) for gait estimation
- Validated against Vicon motion capture — 10 subjects
- Treadmill (3.0 km/h) and overground walking conditions
- Subject-specific spatial calibration via 5-fold LOOCV
- Population-mean K prediction framework for new subjects
  (enables overground validation without treadmill calibration)
- Full statistical analysis: ICC, Bland-Altman, Pearson r, 
  paired t-test, Cohen's d, Grubbs test

---

## Key Gait Parameters Estimated

- Stride duration
- Stance & swing duration  
- Cadence
- Stride length (spatial)

---

## Methods (Brief)

| Component | Treadmill | Overground |
|---|---|---|
| Toe-off detection | Zeni (2008) contralateral HS | Trough-based |
| Stride length | Stance-phase gyro integration | Stance-phase gyro integration |
| K calibration | 5-fold LOOCV per subject | Cohort mean prediction |
| Reference system | Vicon (200 Hz) | Vicon (200 Hz) |

---

## Tech Stack
