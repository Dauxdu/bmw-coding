**English** | [Русский](LDW.ru.md)

# LDW (Lane Departure Warning)

> [!IMPORTANT]
> **KAFAS2, KAFAS, KOMBI** — F-series → KAFAS2; G-series → KAFAS.

---

## Changing the LDW Activation Speed

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3020
Parameters:
- THRV_AVAI_TLC_HIGH → 3C // Upper LDW speed threshold (3C = 60 km/h)
- THRV_AVAI_TLC_LOW → 37  // Lower LDW speed threshold (37 = 55 km/h)
```

> [!NOTE]
> Factory values depend on the market.

### Parameter settings for G-series

```text
ECU: KAFAS → 3103
Parameters:
- LDW_C_THRESHOLD_VELOCITY_AVAILABILITY_HIGH → user // Upper threshold (HEX, km/h)
- LDW_C_THRESHOLD_VELOCITY_AVAILABILITY_LOW → user  // Lower threshold (HEX, km/h)
```

### Speed values

| HEX | km/h |
| :-- | :--- |
| 28  | 40   |
| 32  | 50   |
| 37  | 55   |
| 3C  | 60   |
| 46  | 70   |
| 50  | 80   |

---

## Enabling/Disabling LDW

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3020
Parameters:
- TLC_ON_OFF → TLC_on_F020_F030_F025 // Enable LDW
```

> [!NOTE]
> The KOMBI parameters are only needed when retrofitting LDW. If LDW was
> fitted at the factory, they are already enabled.

---

## Road Edge and Curb Detection

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3000
Parameters:
- ROAD_EDGE_WARNING_ENABLED → 01 // Road edge + curb in LDW (default: road_edge_detection_disabled = 00)
- ROAD_EDGE_DISTANCE_SHIFT       // Road edge threshold offset (default: value_1 = 00 00 00 64)
```

---

## Notes and Troubleshooting

| Problem / Error      | How to check / Solution                               |
| :------------------- | :---------------------------------------------------- |
| LDW does not trigger | Check the speed, TLC_ON_OFF, that the camera is clean |
| False alarms         | Raise the speed thresholds, check the lane markings   |
| KAFAS error          | Calibrate the camera, check its mounting              |

---

> [!WARNING]
> On the F30, `TLC_ON_OFF = 01` (enabled) from the factory. If it is `00`,
> the system will be completely inactive. Parameters may be reset after
> camera calibration.
