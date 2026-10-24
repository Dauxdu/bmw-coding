**English** | [Русский](Exterior-Lights.ru.md)

# Exterior Lights (Brake Lights and Auto Headlights)

> [!IMPORTANT]
> **FEM_BODY** — F-series → FEM_BODY.

---

## Flashing Brake Lights Under Emergency Braking

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- ESS_AKTIVIERBARER_AUSGANG → bremslicht_blinkend // Brake lights flash (default: flaechenvergroesserung)
- ESS_AKTIVIERUNG_GESCHW → user                   // Activation speed threshold (HEX, default: 02)
```

### ESS_AKTIVIERBARER_AUSGANG values

| Behavior                          | Value                  |
| :-------------------------------- | :--------------------- |
| Inner section lights up (default) | flaechenvergroesserung |
| Brake lights flash                | bremslicht_blinkend    |

> [!NOTE]
> In some CAFD versions the parameters are called `ESS_ERSSCHEINUNGSBILD`
> and `ESS_ON_VERZ` (deceleration threshold).

---

## Hazard Lights After Emergency Braking

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- WB_GB_ENABLE → nicht_aktiv // Hazards do NOT turn on after emergency braking (default: aktiv)
```

> [!WARNING]
> Automatic hazard lights warn drivers behind you. Disable them
> deliberately.

---

## Automatic Headlight Sensitivity

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3130
Parameters:
- RLS_DEF_FLC_SCHWELLWERT_SATZ → unempfindlich // Light sensor threshold (default: normal)
```

### Values

| Sensitivity        | Value            |
| :----------------- | :--------------- |
| Very sensitive     | sehr_empfindlich |
| Sensitive          | empfindlich      |
| Standard (default) | normal           |
| Insensitive        | unempfindlich    |
| DRL mode           | Tagfahrlicht     |

> [!NOTE]
> "Sensitive" — the headlights turn on earlier (in brighter conditions).

---

## Notes and Troubleshooting

| Problem / Error              | How to check / Solution                                    |
| :--------------------------- | :--------------------------------------------------------- |
| Brake lights do not flash    | Check the parameter name (ESS\_\* depends on CAFD version) |
| Headlights turn on too early | Select unempfindlich in RLS_DEF_FLC_SCHWELLWERT_SATZ       |
| ECU error                    | Restore the FEM_BODY coding backup                         |

---

> [!WARNING]
> Changing the brake light logic may conflict with your country's traffic
> laws. Check the legislation before changing it.
