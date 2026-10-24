**English** | [Русский](High-Beam-Assistant.ru.md)

# High Beam Assistant (5AC)

> [!IMPORTANT]
> **KAFAS2, FEM_BODY, HU_NBT** — requires a KAFAS2 camera and option 5AC.
> After changing the FA, you must recalculate the FP and code all related
> ECUs.

---

## Activating 5AC (VO Coding)

### Procedure for F-series

```text
1. Open the vehicle FA in E-Sys
2. Remove option 5AP (if present)
3. Add option 5AC
4. Click "Calculate FP"
5. Code the ECUs: FEM_BODY, FLA/KAFAS2
```

> [!NOTE]
> It is also recommended to activate Variable Light Distribution
> (remove 8S4 from the FA → VO code FEM_BODY) for the Active High Beam
> Assistant to work fully.

> [!WARNING]
> Glare-free high beams require adaptive headlights. If KAFAS2 has
> `CAR_WITH_AHL_CURVE_LIGHTS = no_AHL (00)`, the function will most likely
> not work. On the F30, `GLAREFREE_HIGHBEAM_ENABLED = 00` from the factory.

---

## High Beam Activation Speed

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3050
Parameters:
- SPEED_SWITCHING_HIGH_BEAMS_ON → 28  // High beams on at 40 km/h (HEX, default: 28 for all markets)
- SPEED_SWITCHING_HIGH_BEAMS_OFF → 1E // High beams off at 30 km/h (HEX, default: 1E)
```

### Speed values

| HEX | km/h |
| :-- | :--- |
| 14  | 20   |
| 1E  | 30   |
| 28  | 40   |
| 32  | 50   |
| 3C  | 60   |

---

## HBA Parameters in FEM_BODY

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3050
Parameters:
- C_HBA_ENA_V_HI → user   // HBA activation speed (HEX, km/h)
- C_HBA_ENA_V_LO → user   // HBA deactivation speed (HEX, km/h)
- C_HBA_HGWY_V_HI → 8C    // Enter Highway Mode at 140 km/h (default: 8C)
- C_HBA_HGWY_V_LO → 5A    // Exit Highway Mode at 90 km/h (default: 5A)
```

---

## Enabling FLA via the Interface

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3015
Parameters:
- FLA_ON_OFF → FLA_on // Enable the FLA function (default: FLA_on = 01)
```

---

## Notes and Troubleshooting

| Problem / Error          | How to check / Solution                                     |
| :----------------------- | :---------------------------------------------------------- |
| 5AC does not activate    | Check the KAFAS2 camera, option 5AC in the FA, the coding   |
| High beams do not switch | Check the speed, oncoming traffic, that the camera is clean |
| KAFAS error              | Calibrate the camera via service functions                  |

---

> [!WARNING]
> After changing the FA (VO coding), all previous FDL codings in the
> affected ECUs are reset to factory values. Do VO coding before FDL coding.
