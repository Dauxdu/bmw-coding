**English** | [Русский](Turn-Signals.ru.md)

# Turn Signals

> [!IMPORTANT]
> **FEM_BODY, KOMBI, HU_NBT** — F-series → FEM_BODY.
> HUD indication requires the 6WA (Extended) display.

---

## Non-Latching (Soft) Turn Signals

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3075
Parameters:
- FS_TYP_SZL → nicht_rastend // Non-latching turn signal stalk (default: rastend)

ECU: FEM_BODY → 3140
Parameters:
- LIN_VARIANTE_SZL → szl_aic_4Band_fla // SZL variant for soft turn signals
```

### LIN_VARIANTE_SZL breakdown

| Abbreviation | Meaning                         |
| :----------- | :------------------------------ |
| szl          | Steering column formwork center |
| aic          | Automatic interval control      |
| 4Band        | 4-position switch               |
| fla          | Front light assist              |

> [!NOTE]
> A light tap on the stalk turns the signal on for 3–5 flashes without
> latching. Handy for lane changes.

---

## Number of Turn Signal Flashes

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- BLINKZYKLEN_ANZAHL_TIPP → werte=X-1 // Number of flashes (default: 02 = 3 flashes)
```

### Values

| Flashes     | HEX (werte) |
| :---------- | :---------- |
| 3 (default) | 02          |
| 4           | 03          |
| 5           | 04          |

---

## LED Turn Signals (Replacing Bulbs with LEDs)

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3061
Parameters:
- FRA_V_L_KALTUEBERWACHUNG → nicht_aktiv  // Disable cold monitoring, front left
- FRA_V_L_WARMUEBERWACHUNG → nicht_aktiv  // Disable warm monitoring, front left
- FRA_V_L_IS_LED → aktiv                  // Enable LED detection, front left
- FRA_V_R_KALTUEBERWACHUNG → nicht_aktiv  // Disable cold monitoring, front right
- FRA_V_R_WARMUEBERWACHUNG → nicht_aktiv  // Disable warm monitoring, front right
- FRA_V_R_IS_LED → aktiv                  // Enable LED detection, front right

ECU: FEM_BODY/REM → 3061
Parameters:
- FRA_H_L_KALTUEBERWACHUNG → nicht_aktiv  // Disable cold monitoring, rear left
- FRA_H_L_WARMUEBERWACHUNG → nicht_aktiv  // Disable warm monitoring, rear left
- FRA_H_L_IS_LED → aktiv                  // Enable LED detection, rear left
- FRA_H_R_KALTUEBERWACHUNG → nicht_aktiv  // Disable cold monitoring, rear right
- FRA_H_R_WARMUEBERWACHUNG → nicht_aktiv  // Disable warm monitoring, rear right
- FRA_H_R_IS_LED → aktiv                  // Enable LED detection, rear right
```

> [!NOTE]
> Without these parameters, LED bulbs flicker because of the pulsed
> filament check performed every 4 minutes. Recommended bulbs:
> CREE 30W XB-D5 LED.

---

## Turn Signal Indication in the HUD

### Parameter settings for F-series

```text
ECU: HU_NBT → 3001
Parameters:
- HUD_TURNSIGNAL → aktiv // Turn signals in the HUD (Part 1)

ECU: KOMBI → 3008
Parameters:
- HUD_PIA_BLINKER → aktiv // Turn signals in the HUD (Part 2)

ECU: KOMBI → 3000
Parameters:
- BLINKER_HUD_ENABLE → aktiv // Turn signals in the HUD (Part 3)
```

> [!NOTE]
> Only works on 6WA (Extended) displays.

---

## Disabling the Front Side Markers

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3063
Parameters:
- MAPPING_SIDEMARKER_L_OUTPUT → off // Left side marker off (default: fra_v_l)
- MAPPING_SIDEMARKER_R_OUTPUT → off // Right side marker off (default: fra_v_r)
```

> [!NOTE]
> Relevant for US cars with amber side markers in the headlights.
> The turn signal repeater function is kept.

---

## Notes and Troubleshooting

| Problem / Error               | How to check / Solution                                               |
| :---------------------------- | :-------------------------------------------------------------------- |
| Soft turn signals do not work | Check FS_TYP_SZL + LIN_VARIANTE_SZL and steering column compatibility |
| LEDs flicker                  | Check all `FRA_*_IS_LED` and `FRA_*_UEBERWACHUNG` parameters          |
| Turn signals not in the HUD   | Make sure 6WA is present; the function does not work on the F30       |

---

> [!WARNING]
> When installing LED bulbs in the rear turn signals, the `FRA_H_*_IS_LED`
> parameter may trigger the Check Engine Light. Check compatibility with
> your REM firmware version.
