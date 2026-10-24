**English** | [Русский](Safety-Features.ru.md)

# Safety Features

> [!IMPORTANT]
> **ACSM, ICM, KAFAS, HU_NBT, BDC_BODY** — ACSM = safety module;
> ICM = chassis; KAFAS = camera.

---

## Disabling the Seat Belt Reminder

### Parameter settings for F-series

```text
ECU: ACSM → 3000
Parameters:
- SeatBeltReminder_SBR_Fahrer → nicht_aktiv              // Driver reminder (default: aktiv)
- SeatBeltReminder_SBR_Beifahrer → nicht_aktiv           // Passenger reminder (default: aktiv)
- SBR_FA_GWF_SBR_FA → nicht_aktiv                        // Driver reminder (alt.)
- SBR_BF_GWF_SBR_BF → nicht_aktiv                        // Passenger reminder (alt.)
- Initialwarnung_GWF_IW → nicht_aktiv                    // Chime on startup (default: aktiv)
- Gurtzustandsanzeige_Fahrer_GWF_GZA_FA → nicht_aktiv    // Driver belt icon
- Gurtzustandsanzeige_Beifahrer_GWF_GZA_BF → nicht_aktiv // Passenger belt icon
- SBR_PreWarning_Fahrer → nicht_aktiv                    // Sound when unbuckling (driver)
- SBR_PreWarning_Beifahrer → nicht_aktiv                 // Sound when unbuckling (passenger)

ECU: ACSM → 3001
Parameters:
- GWF_SBR_WARNDAUER → werte=01 // Warning duration (default: 5A = 90 s)
```

### Parameter settings for G-series

```text
ECU: FA → HO-WORT
Parameters:
- Add OI11 → Calculate FP → Code ACSM // Disable the belt chime via the FA

ECU: DKOMBI4 → 3000
Parameters:
- FOND_GURTSTATUS_ENABLE → inaktiv // Remove the rear passenger belt icon
```

---

## Removing Disclaimers in iDrive

### Parameter settings for F-series

```text
ECU: HU_NBT → 3001
Parameters:
- LEGAL_DISCLAIMER_TIME → kein_ld        // Remove the disclaimer on iDrive startup
- MACRO_CAM_LEGALDISCLAIMER → kein_ld    // Remove the camera/PDC disclaimer
- MACRO_NIVICAM_LDISCLAIMER → kein_ld    // Remove the Night Vision disclaimer (if 6UK is fitted)
```

---

## Active Blind Spot Detection (Activation Speed)

### Parameter settings for F-series

```text
ECU: ICM → 3000
Parameters:
- C_ZSW_Aktivierunggeschwindigkeit_Funktion_low → 20_kmh // Activation threshold (default: 50_kmh)
```

> [!NOTE]
> Do not set it below 20 km/h. The default is 50 km/h.

---

## Disabling the Horn on Lock (G-series)

### Parameter settings for G-series

```text
ECU: BDC_BODY → 7083
Parameters:
- AM_HORN_AT_SECURE → nicht_aktiv // Remove the horn when locking with the engine running
```

---

## Notes and Troubleshooting

| Problem / Error                  | How to check / Solution                                        |
| :------------------------------- | :------------------------------------------------------------- |
| Belt chime does not turn off     | Check all 9 ACSM parameters + GWF_SBR_WARNDAUER                |
| Disclaimer still shows           | Check LEGAL_DISCLAIMER_TIME + MACRO_CAM_LEGALDISCLAIMER        |
| Blind spot detection not working | Check that the option exists, C_ZSW_Aktivierunggeschwindigkeit |

---

> [!WARNING]
> Disabling seat belt reminders reduces safety. In some countries this may
> be illegal. Use at your own risk.
