**English** | [Русский](Daytime-Running-Lights.ru.md)

# Daytime Running Lights (DRL)

> [!IMPORTANT]
> **FEM_BODY, REM, HU_NBT, BDC_BODY** — F-series → FEM_BODY + REM;
> G-series → BDC_BODY.

---

## DRL Item in the iDrive Menu

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- DAYDRIVING_LIGHT → standart // "DRL" item in the iDrive lighting settings (werte=02)
```

### Parameter settings for G-series

```text
ECU: HU_NBT_EVO → 3000
Parameters:
- DAYDRIVING_LIGHT → standart // "DRL" item in the iDrive lighting settings
```

> [!NOTE]
> After coding: turn off the car → close and open the doors → start it.
> The item will appear in: Settings → Lights → Daytime driving lights.

---

## Enabling the DRL (Operating Mode)

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- TFL_MODUS → Tfl_s // Enable DRL (options: 0=Off, A=Auto, P=Parking, Tfl_s, Drl_s)
```

### TFL_MODUS values

| Mode           | Value         | Description      |
| :------------- | :------------ | :--------------- |
| Off            | 0             | DRL are off      |
| Auto           | A             | DRL in AUTO mode |
| Parking        | P             | DRL when parked  |
| DRL (standard) | Tfl_s / Drl_s | Permanent DRL    |

---

## DRL and Angel Eyes Brightness

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3062
Parameters:
- MAPPING_TAGFAHRL_V_L_PWM_LEVEL_1 → 64 // Left DRL brightness (HEX, 64 = 100%)
- MAPPING_TAGFAHRL_V_R_PWM_LEVEL_1 → 64 // Right DRL brightness (HEX, 64 = 100%)
- MAPPING_STANDL_V_L_PWM_LEVEL_1 → 32   // Left Angel Eyes brightness (HEX, 32 = 50%)
- MAPPING_STANDL_V_R_PWM_LEVEL_1 → 32   // Right Angel Eyes brightness (HEX, 32 = 50%)
- MAPPING_PARKL_V_L_PWM_LEVEL_1 → 32    // Left parking light brightness
- MAPPING_PARKL_V_R_PWM_LEVEL_1 → 32    // Right parking light brightness
```

### Brightness values

| Brightness | HEX |
| :--------- | :-- |
| 0%         | 00  |
| 25%        | 19  |
| 50%        | 32  |
| 100%       | 64  |

> [!NOTE]
> Values are in HEX. Default for DRL = 64 (100%), for Angel Eyes = 08.
> On the F32, Angel Eyes adjustment may not work.

---

## Rear Position Lights with DRL

### Parameter settings for F-series

```text
ECU: REM → 3062
Parameters:
- MAPPING_TAGFAHRL_H_L_OUTPUT → sl_l    // Rear left (outer) with DRL
- MAPPING_TAGFAHRL_H_R_OUTPUT → sl_r    // Rear right (outer) with DRL
- MAPPING_TAGFAHRL_H2_L_OUTPUT → sl_2_l // Rear left (inner) with DRL
- MAPPING_TAGFAHRL_H2_R_OUTPUT → sl_2_r // Rear right (inner) with DRL
```

### Parameter settings for G-series

```text
ECU: BDC_BODY → 3702
Parameters:
- LIC_FEATURE_4 → aktiv // Rear position lights with DRL
```

> [!NOTE]
> With the DRL on, the rear position lights light up for better visibility
> of the car from behind.

### Rear light brightness in DRL mode

```text
ECU: REM → 3062
Parameters:
- MAPPING_TAGFAHRL_H_L_PWM_LEVEL_1 → 64 // Rear left brightness with DRL (HEX, 64 = 100%)
- MAPPING_TAGFAHRL_H_R_PWM_LEVEL_1 → 64 // Rear right brightness with DRL (HEX, 64 = 100%)
```

---

## DRL in the Welcome Light

### Parameter settings for F-series

```text
ECU: FEM_BODY
Parameters:
- MAPPING_TAGFAHRL_V_L_PART_OF_WL → active // Front left DRL in the Welcome Light
- MAPPING_TAGFAHRL_V_R_PART_OF_WL → active // Front right DRL in the Welcome Light

ECU: REM
Parameters:
- MAPPING_TAGFAHRL_H_L_PART_OF_WL → active // Rear left in the Welcome Light
- MAPPING_TAGFAHRL_H_R_PART_OF_WL → active // Rear right in the Welcome Light
```

---

## Notes and Troubleshooting

| Problem / Error                | How to check / Solution                              |
| :----------------------------- | :--------------------------------------------------- |
| iDrive item does not appear    | Cycle the ignition, check the HU_NBT version         |
| DRL brightness does not change | Check the headlight type (LED/Xenon) and PWM support |
| Rear position lights are off   | Check REM → 3062, all 4 MAPPING_TAGFAHRL parameters  |

---

> [!WARNING]
> Disabling the DRL may reduce the car's visibility during the day and
> violate traffic laws in some countries. Check the legislation before
> changing it.
