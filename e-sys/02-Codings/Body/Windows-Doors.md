**English** | [Русский](Windows-Doors.ru.md)

# Windows & Doors

> [!IMPORTANT]
> **FEM_BODY, REM, FRM, BDC_BODY** — F20/F30 → FEM_BODY + REM;
> F01/F10 → FRM; G-series → BDC_BODY.

---

## Windows Work with the Door Open

### Parameter settings for F-series (F20, F30, F34)

```text
ECU: FEM_BODY → 3050
Parameters:
- FH_TUERAUF_STOP_MAUT → nicht_aktiv // Front windows work with the door open

ECU: REM → 3050
Parameters:
- FH_TUERAUF_STOP_MAUT → nicht_aktiv // Rear windows work with the door open
```

### Parameter settings for F-series (F01, F10, F25)

```text
ECU: FRM → 3050
Parameters:
- FH_TUER_AUF_STOP_MAUT → nicht_aktiv // Windows work with the door open
```

### Parameter settings for G-series

```text
ECU: BDC_BODY → 44ED
Parameters:
- FH_TUERAUF_STOP_MAUT → nicht_aktiv // Windows work with the door open
```

> [!NOTE]
> The power windows keep working with the driver's or passenger's door
> open. Handy for airing out the car and for washing.

---

## Comfort Opening/Closing of the Windows from the Key

### Parameter settings for F-series (F20, F30, F34)

```text
ECU: FEM_BODY → 3053
Parameters:
- KOMFORTOEFFNUNG_FB → aktiv       // Open windows by long-pressing "Unlock" on the key
- KOMFORTSCHLIESSUNG_FB → aktiv    // Close windows by long-pressing "Lock" on the key
- KOMFORT_OEFFNEN → werte=0A       // Comfort opening delay (HEX, 0A = 1 s)
- KOMFORT_SCHLIESSEN → werte=00    // Comfort closing delay (00 = no delay)
- KOMFORT_OEFF_HINTEN → werte=05   // Delay between front and rear windows
- KOMFORT_SCHL_VORNE → werte=05    // Delay between front windows when closing
- KOMFORT_OEFF_SHD → werte=23      // Delay between windows and sunroof (if fitted)
- KOMFORT_SCHL_SHD → werte=23      // Delay between windows and sunroof when closing
```

### Delay values

| Delay          | HEX | Seconds |
| :------------- | :-- | :------ |
| No delay       | 00  | 0       |
| Short          | 05  | ~0.5    |
| Medium         | 0A  | ~1      |
| Long (default) | 0F  | ~1.5    |

---

## Unlocking the Doors When the Ignition Is Switched Off

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3040
Parameters:
- CLM_UNLOCK_KL15OFF_AFTER_PIA_AUTO_LOCK → aktiv // Doors unlock when the ignition is switched off
```

> [!NOTE]
> If automatic door locking is enabled, all doors unlock automatically
> when the ignition is switched off.

---

## Automatic Door Locking

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3040
Parameters:
- CLM_TIME_PIA_LOCK_AT_TIMEOUT → werte=0C // Auto-lock after 120 s (HEX, unit = 10 s)
```

---

## Radio Off When a Door Is Opened

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3020
Parameters:
- TCM_LOGIC_R_OFF_DOOR → aktiv // Radio and navigation turn off when the driver's door is opened
```

---

## Number of Turn Signal Flashes on Lock/Unlock

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- QUITTBLK_SICHERN_ANZAHL → werte=X-1      // Flashes on lock (default: 01 = 2 flashes)
- QUITTBLK_ENTSCHAERFEN_ANZAHL → werte=X-1 // Flashes on unlock (default: 02 = 3 flashes)
```

---

## Trunk Opening Delay via Comfort Access

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3040
Parameters:
- CLM_TIMEOUT_HK_SMO → wert_01      // Minimal trunk opening delay (HEX × 0.1 s)
- CLM_SMO_INDICATOR → nicht_aktiv   // Disable tail light flashing when the trunk opens
```

---

## Notes and Troubleshooting

| Problem / Error               | How to check / Solution                                    |
| :---------------------------- | :--------------------------------------------------------- |
| Window does not go up         | Initialize the window: raise → hold 3 s → lower → hold 3 s |
| Doors do not lock             | Check CLM_TIME_PIA_LOCK_AT_TIMEOUT and the fuses           |
| Comfort closing does not work | Check KOMFORTSCHLIESSUNG_FB, cycle the ignition            |

---

> [!WARNING]
> After disconnecting the battery or replacing the FEM_BODY/REM module,
> the power windows must be initialized (a full up/down cycle, holding the
> button for 3 seconds in each position).
