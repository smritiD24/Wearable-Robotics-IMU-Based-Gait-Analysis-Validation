# Hardware

## IMU Sensors

| Property | Details |
|---|---|
| Sensor type | Inertial Measurement Unit (IMU) |
| Configuration | Dual-shank, bilateral (one per leg) |
| Axes used | Gyroscope (angular velocity, deg/s), Accelerometer |
| Primary signal | Sagittal plane angular velocity (wz) |
| Sampling rate | [Your IMU sampling rate, e.g. 100 Hz] |
| Communication | [Wired / Wireless / Bluetooth — fill in] |
| Device model | [Your IMU model — fill in] |

---

## Sensor Placement

- Mounted on the **anterior surface of the shank** (lower leg), bilateral
- Positioned mid-shaft between the knee and ankle
- Secured with an elastic strap to minimise soft-tissue artefact
- Sensor local z-axis (wz) aligned with the mediolateral axis of the shank to capture sagittal plane rotation

**Right leg:** wz1 channel (positive convention maintained)
**Left leg:** wz2 channel (sign inverted in software to match convention)

---

## Reference System — Vicon Motion Capture

| Property | Details |
|---|---|
| System | Vicon (Oxford Metrics) |
| Sampling rate | 200 Hz |
| Markers used | RHEE (right heel), LHEE (left heel), RPSI, LPSI (sacrum) |
| Heel strike detection | Peaks of sacrum-heel AP distance signal |
| Toe-off detection (treadmill) | Zeni (2008) contralateral heel-strike method |
| Toe-off detection (overground) | Trough of sacrum-heel AP distance signal |

---

## Treadmill

| Property | Details |
|---|---|
| Model | [Your treadmill model — fill in] |
| Speed | 3.0 km/h (fixed, steady-state) |
| Belt direction | Anteroposterior |

---

## Notes

- IMU and Vicon clocks are independent — time synchronisation performed in software by aligning the first right heel strike detected by both systems
- Growing timing error (clock drift) between IMU and Vicon is expected and documented, particularly across overground laps
