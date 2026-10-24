**English** | [Русский](FCW.ru.md)

# FCW (Forward Collision Warning)

> [!IMPORTANT]
> **KAFAS2, ICM, KOMBI** — KAFAS2 = camera; ICM = chassis; KOMBI = display.

---

## Warning Parameters

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3060
Parameters:
- speed_thrv_fcw_acute_dynamic → 0A    // Speed threshold for the "acute" warning (default: 0F)
- speed_thrv_fcw_advance_dynamic → 0A  // Threshold for the "advance" warning (default: 0F)
- min_time_advance_warn → 0A           // Min. time before the early warning (default: 0F)
- min_time_acute_warn → 0F             // Min. time for the acute warning (default: 14)
- max_dist_acute → 55                  // Max. acute warning distance (default: 46)
```

> [!NOTE]
> `driver_warning` in the CAFD has a single option `default` (AB) —
> it is a bit mask with no documented variants. The value `FF` is
> undocumented and its effect is unconfirmed.

---

## TTC (Time-To-Collision) Parameters

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3070
Parameters:
- TTC_THRV_ADV_EARLY → 3C               // Early warning TTC (default: 30)
- TTC_THRV_ACUTE_EARLY → 30             // Acute warning TTC (default: 20)
- TTC_THRV_SHIFT_BRAKE_ACUTE_EARLY → 28 // TTC while braking, early (default: 1E)
- TTC_THRV_SHIFT_BRAKE_ACUTE_LATE → 28  // TTC while braking, late (default: 1E)
```

> [!NOTE]
> **Time-To-Collision** is the estimated time until a collision. The warning
> fires when TTC drops below the threshold, so a larger value = an earlier
> warning. Values are HEX.

---

## Notes and Troubleshooting

| Problem / Error         | How to check / Solution                                  |
| :---------------------- | :------------------------------------------------------- |
| Warnings do not trigger | Check speed, distance and the FCW_CODING parameters      |
| Too many false alarms   | Lower the TTC thresholds, revert values to default       |
| KAFAS error             | Calibrate the camera, check that the windshield is clean |

---

> [!WARNING]
> Do not set the parameters too "early" — this will cause constant false
> alarms. Change values gradually.
