**English** | [Русский](Service-Intervals.ru.md)

# Service Intervals (FA Codes)

> [!IMPORTANT]
> **FA (Vehicle Order)** — service interval codes are added via the FA
> editor in E-Sys.

---

## Service Interval Codes

| Code    | Interval              | Description       |
| :------ | :-------------------- | :---------------- |
| **8KA** | 30,000 km / 24 months | Longlife maximum  |
| **8KB** | 25,000 km / 24 months | Longlife          |
| **8KC** | 24,000 km / 24 months | Standard          |
| **8KD** | 12,000 km / 24 months | Shortened         |
| **8KE** | 30,000 km / 12 months | Time-based        |
| **8KF** | 25,000 km / 12 months | Time-based        |
| **8KG** | 20,000 km / 18 months | Compromise        |
| **8KH** | 20,000 km / 12 months | Frequent          |
| **8KK** | 15,000 km / 18 months | Shortened         |
| **8KL** | 15,000 km / 12 months | Frequent (city)   |
| **8KM** | 12,000 km / 12 months | Very frequent     |
| **8KN** | 10,000 km / 12 months | Severe conditions |
| **8KP** | 8,000 km / 12 months  | Most frequent     |

---

## How to Apply

```text
1. Open the vehicle in E-Sys
2. Go to the FA editor
3. Add the required code (e.g. 8KL)
4. Remove the old interval code (if any)
5. Click "Calculate FP"
6. Code the ECUs: DDE/DME, KOMBI
```

---

## Choosing a Code

| Operating conditions           | Recommended code |
| :----------------------------- | :--------------- |
| City, short trips              | 8KL / 8KM        |
| Mixed driving                  | 8KC / 8KD        |
| Highway, calm driving          | 8KA / 8KB        |
| Severe conditions (dust, cold) | 8KN / 8KP        |

---

## Notes and Troubleshooting

| Problem / Error         | How to check / Solution                                     |
| :---------------------- | :---------------------------------------------------------- |
| Interval did not change | Check that the old code was removed and the FP recalculated |
| Error when coding DME   | Make sure: engine OFF, ignition ON                          |

---

> [!WARNING]
> Code DDE/DME and KOMBI strictly with the **engine off** and the
> **ignition on**. After an oil change, reset the service indicator via the
> service menu or a diagnostic scanner.
