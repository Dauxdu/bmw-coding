**English** | [Русский](Mirrors.ru.md)

# Mirrors

> [!IMPORTANT]
> **FEM_BODY, BDC_BODY** — F-series → FEM_BODY; G-series → BDC_BODY.

---

## Folding/Unfolding the Mirrors from the Key

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3110
Parameters:
- ASP_AUSKLAPPEN_NACH_KOMFORTSCHLIESSEN → aktiv // Unfold mirrors on unlock
- ASP_BEIKLAPPEN_BEI_KOMFORTSCHLIESSEN → aktiv  // Fold mirrors on lock
- ASP_GESCHWINDIGKEIT_AUTO_AUSKLAPPEN → 14      // Auto-unfold at 20 km/h (HEX)
- ASP_MAX_GESCHWINDIGKEIT_BEIKLAPPEN → FF       // Max. folding speed (FF = 255 km/h)
```

### Speed values

| Speed             | HEX |
| :---------------- | :-- |
| 20 km/h           | 14  |
| 40 km/h (default) | 28  |
| No limit          | FF  |

> [!NOTE]
> `ASP_MAX_GESCHWINDIGKEIT_BEIKLAPPEN` must be ≥ the value of
> `ASP_GESCHWINDIGKEIT_AUTO_AUSKLAPPEN`. The mirrors fold when the "Lock"
> button on the key is held and unfold on unlock or when the set speed
> is reached.

---

## Passenger Mirror Parking Tilt (G-series)

### Parameter settings for G-series

```text
ECU: BDC_BODY → 3110
Parameters:
- ASP_BORDSTEINAUTOMATIK_DELTA → 5A // Right mirror tilt angle in reverse gear
```

### Angle values

| Tilt angle    | Value (HEX) |
| :------------ | :---------- |
| 90° (default) | 5A          |
| 80°           | 50          |
| 70°           | 46          |
| 59°           | 3B          |

> [!NOTE]
> When reverse gear is engaged, the right mirror tilts down to show the
> curb. It returns to its original position above 15–20 km/h or when
> shifting to D/P.

---

## Notes and Troubleshooting

| Problem / Error       | How to check / Solution                                                  |
| :-------------------- | :----------------------------------------------------------------------- |
| Mirror does not tilt  | Check ASP_BORDSTEINAUTOMATIK_DELTA, run the mirror adaptation            |
| Mirrors do not fold   | Check ASP_BEIKLAPPEN_BEI_KOMFORTSCHLIESSEN and that power folding exists |
| Mirrors do not unfold | Check ASP_GESCHWINDIGKEIT_AUTO_AUSKLAPPEN                                |

---

> [!WARNING]
> After changing mirror parameters, it is recommended to calibrate them
> via the service menu or a diagnostic scanner.
