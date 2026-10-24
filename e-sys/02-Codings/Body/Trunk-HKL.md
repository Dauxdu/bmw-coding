**English** | [Русский](Trunk-HKL.ru.md)

# Trunk (HKL / HKFM)

> [!IMPORTANT]
> **HKFM, HKL, FEM_BODY** — HKFM = tailgate drive module;
> HKL = tailgate controller; FEM_BODY = Comfort Access delays.

---

## Smooth Trunk Opening (No Bump)

### Parameter settings for F-series

```text
ECU: HKFM → 3010
Parameters:
- DREHZAL_SEGMENT_OEFF → 50 58 58 58 58 58 58 58 45 // Smooth opening without a bump
```

---

## Smooth Trunk Closing (No Bump)

### Parameter settings for F-series

```text
ECU: HKFM → 3010
Parameters:
- DREHZAL_SEGMENT_SCHL → 20 30 58 58 58 58 58 58 45 // Smooth closing without a bump
```

> [!NOTE]
> The 9-byte array sets the drive speed profile for each segment of travel.
> Changing the first bytes affects the start/end section.

---

## Closing the Trunk from the Cabin Button and the Key

### Parameter settings for F-series

```text
ECU: HKFM → 3010
Parameters:
- SCH_FBD → aktiv      // Close the trunk with the key button
- SCH_TOEHKI → aktiv   // Close the trunk with the cabin button (driver's footwell)
- TASTER_FBD → aktiv   // Required for SCH_FBD and SCH_TOEHKI to work
```

> [!NOTE]
> `TASTER_FBD` is required. Without it, `SCH_FBD` and `SCH_TOEHKI`
> will not activate.

---

## Closing the Trunk Without Delay (Cabin Button / Key)

### Parameter settings for F-series

```text
ECU: HKL → 3010
Parameters:
- HKL_ROCKERSWITCHPOS2_LONGPRESS_CLOSE → 00            // No hold required (cabin button)
- HKL_ROCKERSWITCHPOS2_DELAY_CLOSE → 00, 00            // No delay (cabin button)
- HKL_REMOTECONTROLLIFTGATEBUTTON_LONGPRESS_CLOSE → 00 // No hold required (key)
- HKL_REMOTECONTROLLIFTGATEBUTTON_DELAY_CLOSE → 00, 00 // No delay (key)
```

---

## Comfort Control from the Key

### Parameter settings for F-series

```text
ECU: HKL → 3010
Parameters:
- KOMFORT_OEFFNEN_HKL → aktiv       // Open by long-pressing "Unlock" on the key
- KOMFORT_SCHLIESSEN_HKL → aktiv    // Close by long-pressing "Lock" on the key
- FUNKTION_FBD_SCHLIESSEN_2 → aktiv // Close with a single press of the key button
- FUNKTION_TOEHKI → aktiv           // Close with the button in the driver's footwell
```

---

## Reducing the Opening Delay from the Key

### Parameter settings for F-series

```text
ECU: FEM_BODY → 30D0
Parameters:
- RC_TIME_DELAY_BOOTLID → lower Werte // Reduce the trunk opening delay from the key
```

---

## Notes and Troubleshooting

| Problem / Error               | How to check / Solution                                           |
| :---------------------------- | :---------------------------------------------------------------- |
| Smooth closing does not work  | Check the HKL calibration, run the drive adaptation               |
| Cabin button does not respond | Check SCH_TOEHKI + TASTER_FBD and that the physical button exists |
| Delay when opening from key   | Decrease RC_TIME_DELAY_BOOTLID in FEM_BODY                        |

---

> [!WARNING]
> After changes to HKFM/HKL, run the tailgate mechanism adaptation via
> E-Sys service functions (Service Functions → HKL → Adaptation).
