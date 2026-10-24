**English** | [Русский](HUD.ru.md)

# HUD (Head-Up Display)

> [!IMPORTANT]
> **KOMBI, HU_NBT, HU_CIC** — HUD parameters live in KOMBI and the HU,
> not in a separate "HUD" module.

---

## Junction View on the HUD

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- JUNCTION_VIEW_HUD → aktiv // Junction images on the HUD (default: nicht_aktiv)
```

---

## ACC Distance (iBrake) in the HUD

### Parameter settings for F-series

```text
ECU: HU_CIC → 3000
Parameters:
- HUD_DISTANCE_INFO → aktiv // ACC distance in the HUD — Part 1

ECU: KOMBI → 3008
Parameters:
- HUD_PIA_IBRAKE → aktiv // ACC distance in the HUD — Part 2

ECU: KOMBI → 3000
Parameters:
- IBRAKE_ABSTAND_ENABLE → aktiv // ACC distance in the HUD — Part 3
```

---

## Entertainment and Phone in the HUD

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- HUD_ENTERTAINMENT_ENABLE → aktiv   // Entertainment menu in the HUD
- HUD_TELEFONANRUF_ENABLE → aktiv    // Call list in the HUD
- HUD_SPRACHEINGABE_ENABLE → aktiv   // Voice commands in the HUD
```

### Parameter settings for F-series (HU_CIC)

```text
ECU: HU_CIC → 3000
Parameters:
- HUD_ENTERTAINMENTLIST → aktiv // "Entertainment/Telephone" checkbox in the HUD settings
```

---

## HUD Splash Screen Duration

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- HUD_START_UP_SCREEN_ANZ_ZEIT → user // HUD splash screen time in seconds (default: 3)
```

---

## Notes and Troubleshooting

| Problem / Error      | How to check / Solution                                   |
| :------------------- | :-------------------------------------------------------- |
| HUD does not turn on | Check power, that the HUD option exists, firmware version |
| Blurry image         | Calibrate position and focus via the service menu         |
| Junctions not shown  | Check JUNCTION_VIEW_HUD, map updates                      |

---

> [!WARNING]
> Most HUD functions are already active on F30/F32 from 2013 onward.
> Check the current parameter values before coding.
