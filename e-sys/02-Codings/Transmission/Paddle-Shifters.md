**English** | [Русский](Paddle-Shifters.ru.md)

# Paddle Shifters

> [!IMPORTANT]
> **FEM_BODY, EGS** — F-series → FEM_BODY + EGS.
> Requires physical paddles on the steering wheel.

---

## Activating Paddle Shifting

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3190
Parameters:
- Paddles_verbaut → aktiv // Activate the paddles (default: nicht_aktiv)

ECU: EGS → 3000
Parameters:
- Sportschalter → aktiv     // Sport shift logic
- Sportschalter_alt → aktiv // Sport shift logic (alternative)
- Applikation_LC → aktiv    // Launch Control (requires 2TB in the FA)
```

> [!NOTE]
> The steering wheel paddles let you shift gears manually regardless of
> the transmission mode. For full functionality, it is recommended to
> activate Sport Auto Transmission (2TB in the FA).

---

## Notes and Troubleshooting

| Problem / Error        | How to check / Solution                                      |
| :--------------------- | :----------------------------------------------------------- |
| Paddles do not respond | Check Paddles_verbaut and that the physical paddles exist    |
| Shifts are ignored     | Check the transmission mode, Sportschalter in EGS            |
| ECU error              | Run the transmission adaptation, check version compatibility |

---

> [!WARNING]
> If there are no paddles on the steering wheel, coding will not add them.
> A paddle kit must be installed and the steering column switch (SZL) may
> need to be replaced.
