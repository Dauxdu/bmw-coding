**English** | [Русский](Headlamp-Washers.ru.md)

# Headlamp Washers

> [!IMPORTANT]
> **FEM_BODY** — requires headlamp washers to be installed (Cold Weather Package).

---

## Disabling the Headlamp Washers Completely

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3080
Parameters:
- WW_SCHEINWERFERREINIGUNG → nicht_aktiv // Disable completely (default: aktiv)
```

---

## Fine-Tuning the Washers

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3080
Parameters:
- WW_ANZAHL_SPRITZIMPULSE_SRA → 3_Impulse          // Number of spray pulses (default: 2_Impulse)
- WW_ANZAHL_WASCHBET_ZUR_SRA → user                // Number of windshield washes before activation (default: 10)
- WW_DAUER_SPRITZIMPULSE_SRA → werte=0A            // Pulse duration (HEX × 100 ms, default: 0A = 1000 ms)
- WW_SRA_GESCHWINDIGKEITS_DEAKTIVIERUNG → werte=82 // Max. activation speed (HEX, default: 82 = 130 km/h)
- WW_PAUSE_SPRITZIMPULSE_SRA → werte=0A            // Pause between pulses (HEX × 100 ms)
- WW_SRA_SPERRZEIT → werte=0A                      // Time before re-activation (HEX × 1 min)

ECU: FEM_BODY → 3081
Parameters:
- WW_ANZAHL_NACHWISCHZ_FRONT → 3_mal_Nachwischen   // Number of wiper passes after washing
```

---

## Wipers Finish Their Cycle After Ignition Off

### Parameter settings for F-series

```text
ECU: FEM_BODY
Parameters:
- WW_ZYCLUS_VOLLEND_KLR_AUS → aktiv // Wipers do not stop mid-glass when the ignition is switched off
```

---

## Notes and Troubleshooting

| Problem / Error        | How to check / Solution                                          |
| :--------------------- | :--------------------------------------------------------------- |
| Washers do not work    | Check WW_SCHEINWERFERREINIGUNG and that the option is installed  |
| Activates too often    | Increase WW_ANZAHL_WASCHBET_ZUR_SRA                              |
| High fluid consumption | Decrease WW_ANZAHL_SPRITZIMPULSE_SRA, WW_DAUER_SPRITZIMPULSE_SRA |

---

> [!WARNING]
> Disabling the headlamp washers reduces safety in winter.
> Headlights can get dirty and lose effectiveness.
