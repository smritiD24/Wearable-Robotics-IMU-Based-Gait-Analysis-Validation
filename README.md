# Dual-Shank IMU-Based Gait Analysis & Validation

**MSc Thesis Project — Human-Centred Robotics Lab, IIT Gandhinagar**

> ⚠️ This study is currently under preparation for publication. Code and data will be made available upon acceptance.

---

## Overview

This repository documents the gait analysis pipeline developed as part of my MSc thesis. The study proposes and validates a dual shank-mounted IMU system for estimating spatial and temporal gait parameters, benchmarked against Vicon motion capture (gold standard) across 10 healthy subjects during treadmill and overground walking.

---

## Research Summary

- Dual IMU system (shank-mounted, bilateral) for gait parameter estimation
- Validated against Vicon motion capture across 10 healthy subjects
- Treadmill (3.0 km/h) and overground walking conditions
- Subject-specific spatial calibration factor K via 5-fold Leave-One-Out Cross-Validation (LOOCV)
- Population-mean K prediction framework — enables overground validation of new subjects without requiring treadmill calibration
- Full statistical analysis: ICC(2,1), Bland-Altman, Pearson r, paired t-test, one-sample t-test, Cohen's d, Grubbs outlier test

---

## Key Gait Parameters Estimated

- Stride duration (s)
- Stance duration (s)
- Swing duration (s)
- Cadence (steps/min)
- Stride length (m)

---

## Methods

| Component | Treadmill | Overground |
|---|---|---|
| Toe-off detection (Vicon) | Zeni (2008) contralateral heel-strike method | Trough-based (argmin between consecutive HS) |
| Stride length estimation | Stance-phase gyroscope integration | Stance-phase gyroscope integration |
| Spatial calibration K | 5-fold LOOCV per subject | Cohort mean prediction (treadmill-free) |
| Reference system | Vicon (200 Hz) | Vicon (200 Hz) |
| Trim | 25 s steady-state | Full trial |

### Stride Length Formula

```
stride_length = K × 2 × leg_length × sin(|∫ω dt| / 2)
```

Where ω is the shank angular velocity (deg/s) integrated over the stance phase, K is the subject-specific or cohort-mean calibration factor, and leg_length is measured from greater trochanter to lateral malleolus.

---

## Hardware

See [HARDWARE.md](HARDWARE.md) for full sensor specifications and placement protocol.

---

## Experimental Protocol

See [PROTOCOL.md](PROTOCOL.md) for participant inclusion criteria, data collection procedure, and trial structure.

---

## Tech Stack

```
Python 3.12
pandas | numpy | scipy | matplotlib
```

---

## Repository Structure

```
├── README.md               # Project overview (this file)
├── HARDWARE.md             # Sensor specifications and placement
├── PROTOCOL.md             # Experimental protocol
├── requirements.txt        # Python dependencies
└── .gitignore              # Prevents accidental data upload
```

> Code will be added upon publication.

---

## Status

- [x] Data collection complete (n=10)
- [x] Treadmill validation complete
- [x] Overground validation complete
- [x] Statistical analysis complete
- [ ] Manuscript under preparation
- [ ] Code release pending publication

---

## Author

**Smriti Dandin**
MSc Student, Human-Centred Robotics Lab
Indian Institute of Technology Gandhinagar

---

## Supervisor

[Your Supervisor's Name]
Human-Centred Robotics Lab, IIT Gandhinagar

---

## Contact

[Your institutional email]
[Your LinkedIn URL]
