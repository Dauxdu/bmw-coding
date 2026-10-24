**English** | [Русский](Radio-Settings.ru.md)

# Radio Settings

> [!IMPORTANT]
> **HU_NBT, HU_CIC** — depending on the head unit generation.

---

## Radio Region

### Parameter settings for F-series

```text
ECU: HU_NBT
Parameters:
- RADIO_COUNTRY → ece // Region: Europe/Russia (options: ece, usa, jpn, kor)
```

---

## FM Frequency Response

### Parameter settings for F-series

```text
ECU: HU_NBT
Parameters:
- FM_DEEMPHASIS → 50us // Standard for Europe and Russia (75us = USA)
```

---

## Frequency Display in MHz

### Parameter settings for F-series

```text
ECU: HU_NBT
Parameters:
- ANZEIGE_FREQ → nicht_aktiv // Frequency in MHz (101.2) instead of kHz (10120)
```

---

## Weather Band (HU_CIC, USA)

### Parameter settings for F-series

```text
ECU: HU_CIC → 3002
Parameters:
- RADIO_WEATHERBAND → aktiv // NOAA Weatherband in the radio sources
```

---

## Notes and Troubleshooting

| Problem / Error        | How to check / Solution           |
| :--------------------- | :-------------------------------- |
| Poor radio reception   | Check the antenna, RADIO_COUNTRY  |
| Distorted sound        | Set FM_DEEMPHASIS → 50us (Europe) |
| Station name not shown | Check the station signal (RDS)    |

---

> [!WARNING]
> Changing the region may affect the available frequency bands and RDS
> functionality. Save the original values before changing them.
