# Experimental Protocol

## Participants

| Property | Details |
|---|---|
| Sample size | 10 healthy adults |
| Inclusion criteria | No neurological, musculoskeletal, or gait-affecting conditions |
| Exclusion criteria | History of lower-limb injury, surgery, or chronic pain affecting walking |
| Anthropometric measure | Leg length (greater trochanter to lateral malleolus, metres) |

---

## Pre-Trial Setup

1. Participant briefed and written consent obtained
2. Leg length measured bilaterally (greater trochanter to lateral malleolus)
3. Vicon reflective markers placed on: RHEE, LHEE, RPSI, LPSI
4. IMU sensors strapped to anterior shank surface, bilateral
5. 10-second static standing calibration performed before walking trials

---

## Treadmill Protocol

| Parameter | Value |
|---|---|
| Speed | 3.0 km/h |
| Duration | ~3–4 minutes continuous walking |
| Trim | First 25 seconds discarded (acceleration to steady state) |
| Vicon toe-off method | Zeni (2008) contralateral heel-strike |
| K calibration | 5-fold LOOCV on treadmill strides |

**Trial structure:**
- Participant walks on treadmill at 3.0 km/h
- IMU and Vicon record simultaneously throughout
- First 25 s trimmed from analysis to ensure steady-state gait only

---

## Overground Protocol

| Parameter | Value |
|---|---|
| Walking condition | Self-selected comfortable pace |
| Track | Straight walkway within Vicon capture volume |
| Laps | Multiple (5 laps recorded per subject) |
| Vicon toe-off method | Trough-based (argmin between consecutive HS) |
| K used | Transferred from treadmill LOOCV (same session) |

**Trial structure:**
- Participant walks at self-selected pace along a straight path
- Vicon captures each lap separately (limited by capture volume)
- Laps are time-stitched in software with a 2-second inter-lap gap assumption
- IMU records continuously across all laps
- Clock drift between IMU and Vicon across laps is documented and reported

---

## K Calibration Factor

The spatial calibration factor K converts IMU angular velocity integration into stride length. Two approaches were used:

**Per-subject (treadmill):**
K estimated from the subject's own treadmill strides using 5-fold time-based LOOCV. Right and left legs calibrated independently (K_Right, K_Left).

**Population mean (treadmill-free):**
For new subjects where treadmill calibration is not available, K is predicted as the cohort mean (K_Right = 0.896, K_Left = 0.890, n=8 subjects excluding statistical outlier S9). Validated via LOOCV and held-out subject testing (S10).

---

## Statistical Analysis

All statistics computed in Python (SciPy). Significance level α = 0.05 (two-tailed).

| Test | Purpose |
|---|---|
| Paired t-test | IMU vs Vicon mean comparison per parameter |
| One-sample t-test | Test whether mean error differs significantly from zero |
| ICC(2,1) | Absolute agreement, two-way mixed model |
| Pearson r | Correlation between IMU and Vicon stride lengths |
| Bland-Altman | Bias and limits of agreement for stride length |
| Cohen's d | Effect size for significant differences |
| Grubbs test | Formal outlier detection for K calibration factor |

---

## Notes

- Subject S9 identified as a formal statistical outlier (Grubbs z = 3.90, threshold = 2.29 at α = 0.05) based on K > 1, likely due to sensor placement or soft-tissue artefact. Results reported both with and without S9.
- Overground spatial MAE is substantially higher than treadmill due to: (1) limited Vicon capture volume reducing matched stride count, (2) inter-lap clock drift, and (3) K calibrated on treadmill conditions which may not fully transfer to free walking kinematics.
