**English** | [Русский](Comfort-Features.ru.md)

# Comfort Features

> [!IMPORTANT]
> **IHKA, FEM_BODY, HU_NBT** — a summary of comfort features.

---

## A/C State Memory

### Parameter settings for F-series

```text
ECU: IHKA → 3002
Parameters:
- MEMORY_OFF → aktiv // Remember the A/C state (default: nicht_aktiv)
```

> [!NOTE]
> The A/C remembers its On/Off state from the previous trip.
> On some cars with `MEMORY_OFF → aktiv` the A/C may always start in the
> Off state.

---

## AUTO Button Does Not Turn On the A/C

### Parameter settings for F-series

```text
ECU: IHKA → 3002
Parameters:
- AC_NICHT_EIN_BEI_AUTO → aktiv // default: nicht_aktiv
```

---

## Air Recirculation Memory

### Parameter settings for F-series

```text
ECU: IHKA → 3003
Parameters:
- MEMORY_UMLUFT → aktiv // Remember recirculation (default: nicht_aktiv)
```

---

## Seat Heating Temperature

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3090
Parameters:
- TEMP_LEHNE_STUFE_1_FRONT → werte=96 // Front backrest, level 1 (default: 95°F)
- TEMP_LEHNE_STUFE_2_FRONT → werte=A2 // Front backrest, level 2 (default: 106°F)
- TEMP_LEHNE_STUFE_3_FRONT → werte=AE // Front backrest, level 3 (default: 116°F)
- TEMP_SITZ_STUFE_1_FRONT → werte=94  // Front seat, level 1 (default: 94°F)
- TEMP_SITZ_STUFE_2_FRONT → werte=A0  // Front seat, level 2 (default: 104°F)
- TEMP_SITZ_STUFE_3_FRONT → werte=AC  // Front seat, level 3 (default: 114°F)
- TEMP_LEHNE_STUFE_1_FOND → werte=96  // Rear backrest, level 1
- TEMP_LEHNE_STUFE_2_FOND → werte=A2  // Rear backrest, level 2
- TEMP_LEHNE_STUFE_3_FOND → werte=AE  // Rear backrest, level 3
- TEMP_SITZ_STUFE_1_FOND → werte=94   // Rear seat, level 1
- TEMP_SITZ_STUFE_2_FOND → werte=A0   // Rear seat, level 2
- TEMP_SITZ_STUFE_3_FOND → werte=AC   // Rear seat, level 3
```

### Value formula

```text
HEX = (Temperature_°C + 40) × 2
Example: 41°C → (41 + 40) × 2 = 162 (dec) = A2 (hex)
```

---

## Easy Entry

### Parameter settings for F-series

```text
ECU: SM2 → 3000
Parameters:
- EINAUSSTIEGSHILFE → Modus_FA_SLV // The seat moves back when the ignition is switched off
- MEMORY_GONG → aktiv              // Chime when saving the seat memory
```

---

## Audible Lock Confirmation

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- ACOUSTICAL_LOCK_CONFIRM → aktiv // Sound when arming/disarming the alarm
```

### Parameter settings for G-series

```text
ECU: HU_MGU → 3000
Parameters:
- Acoustical_lock_confirm → aktiv // Sound when arming/disarming the alarm
```

---

## Notes and Troubleshooting

| Problem / Error                    | How to check / Solution                                |
| :--------------------------------- | :----------------------------------------------------- |
| A/C is always off                  | Check MEMORY_OFF; behavior may vary                    |
| Seat heating temperature unchanged | Check that seat heating exists and the FEM_BODY values |
| Easy Entry does not work           | Check that SM2 and power seats exist                   |

---

> [!WARNING]
> Changing the seat heating temperature affects comfort and safety.
> Do not set values above AE (116°F / 47°C).
