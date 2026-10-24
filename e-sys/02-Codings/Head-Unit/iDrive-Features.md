**English** | [Русский](iDrive-Features.ru.md)

# iDrive Features

> [!IMPORTANT]
> **HU_NBT, HU_CIC, CMB_MEDIA** — depending on the head unit generation.
> Not all HU_CIC parameters work on HU_NBT and vice versa.

---

## Tire Temperature and Pressure in iDrive

### Parameter settings for F-series

```text
ECU: HU_NBT → 3001
Parameters:
- RDC_DRUCK_TEMP → druck_und_temperatur // Tire temperature + pressure (default: druck)
```

> [!NOTE]
> Requires pressure sensors with temperature support (option 2VB).

---

## Voice Control

### Parameter settings for F-series

```text
ECU: CMB_MEDIA → 3000
Parameters:
- SYS_EIN_AUS → aktiv // Basic voice recognition

ECU: HU_NBT → 3003
Parameters:
- CE_DEVICE_SPEECH_RECONGNITION → aktiv // Siri Eyes-Free (hold the voice button)
```

---

## Route and Navigation

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- ROUTE_FLIGHT → aktiv               // "Route preview" simulator — Part 1
- NAVI_SCROLLING_ALONG_ROUTE → aktiv // Route simulator — Part 2
- NAVI_ROAD_PREVIEW → aktiv          // "Route Info" (list of maneuvers)
- NAVI_AUTOZOOM → aktiv              // Auto-zoom when approaching a turn

ECU: HU_NBT → 3001
Parameters:
- NAVI_TRIP_IMPORT → aktiv // Import a route via USB
```

---

## Showing the Full SMS Text

### Parameter settings for F-series

```text
ECU: HU_NBT → 3003
Parameters:
- PIM_Driving_Text → Whole_text // Full SMS message (default: up_to_three_lines)
```

---

## Ringtone and Inband Ringing

### Parameter settings for F-series

```text
ECU: CMB_MEDIA → 3001
Parameters:
- INBAND_RINGING → aktiv   // Phone's own ringtone (works on iPhone, not on Android)
- RINGTONE → ring_tone2    // Ringtone choice (if Inband Ringing is off)
```

---

## Maximum Volume on Startup

### Parameter settings for F-series (HU_CIC)

```text
ECU: HU_CIC → 3002
Parameters:
- VOL_MAX_ON → 32 // Volume up to 100% on startup (default: 19 = 25%)
```

---

## Developer Menu

### Parameter settings for F-series (HU_CIC)

```text
ECU: HU_CIC → 3000
Parameters:
- ENTWICKLER_MENUE → aktiv // Developer menu in settings (Build/Date/Versions)
```

---

## Service History

### Parameter settings for F-series

```text
ECU: HU_NBT / HU_CIC → 3000
Parameters:
- SERVICE_HISTORY → aktiv // Dealer service history in iDrive (default: nicht_aktiv)
```

---

## Notes and Troubleshooting

| Problem / Error             | How to check / Solution                         |
| :-------------------------- | :---------------------------------------------- |
| Tire temperature not shown  | Check RDC_DRUCK_TEMP and that 2VB sensors exist |
| Voice control does not work | Check SYS_EIN_AUS and that a microphone exists  |
| Route does not import       | Check NAVI_TRIP_IMPORT and the file format      |

---

> [!WARNING]
> Not all HU_CIC parameters are compatible with HU_NBT. Check the head
> unit type before coding.
