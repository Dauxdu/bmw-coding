**English** | [Русский](Sport-Features.ru.md)

# Sport Features

> [!IMPORTANT]
> **HU_NBT, KOMBI, ASD, ICM, EGS** — a summary of sport features.

---

## M-Style Sport Gauges

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- M_VEHICLE → aktiv // Sport Display gauge color: red/silver (default: nicht_aktiv)
```

> [!NOTE]
> Changes the gauge color in the sport displays from amber (BMW) to
> red/silver (M style).

---

## Notification Sound (Chime)

### Parameter settings for F-series

```text
ECU: HU_NBT → 3002
Parameters:
- SOUND_SIGNAL_SET → 03_BMW_i // Notification sound (default: 00_BMW)
```

### SOUND_SIGNAL_SET values

| Sound         | Value       |
| :------------ | :---------- |
| BMW (default) | 00_BMW      |
| BMW i         | 03_BMW_i    |
| Mini          | mini        |
| Rolls-Royce   | rolls_royce |

---

## Active Sound Design (ASD)

### Parameter settings for F-series

```text
ECU: ASD → 3000
Parameters:
- Model Range → F010  // Model range (default: F030)
- Engine → S63B44     // Engine sound (default: N26B20)
```

### ASD values

| Model     | Model Range | Engine | Sound         |
| :-------- | :---------- | :----- | :------------ |
| M5/M6     | F010        | S63B44 | V8 Twin-Turbo |
| M3/M4     | F080        | S55B30 | I6 Twin-Turbo |
| 328i/428i | F030        | N26B20 | I4 Turbo      |
| ASD Off   | F020        | S63B44 | Off           |

> [!NOTE]
> ASD is only available on F3x 2014+ with N20 and some N55 engines.
> If the ASD module is visible in E-Sys, it can be modified.

---

## ASD Menu in iDrive

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- ASD_CONFIGURATION → aktiv // ASD settings menu in iDrive — Part 1
- ASD_SOUND_4 → aktiv       // ASD settings menu in iDrive — Part 2
```

---

## iDrive Startup Animation

### Parameter settings for F-series

```text
ECU: HU_NBT → 3001
Parameters:
- STARTUP_EMBLEM → variant_1 // Startup animation (default: variant_0)
- STARTUP_TYPE → black       // Splash screen type (default: animation)
```

### STARTUP_EMBLEM values

| Animation           | Value                           |
| :------------------ | :------------------------------ |
| BMW Connected Drive | variant_0, variant_2, variant_6 |
| ///M                | variant_1                       |
| BMW i               | variant_3                       |
| Mini                | variant_4                       |
| Rolls-Royce         | variant_5                       |
| BMW White           | variant_7                       |
| BMW Brown           | variant_8                       |
| Merry Christmas     | variant_9                       |

### Parameter settings for G-series

```text
ECU: HU_MGU → 3000
Parameters:
- STARTUP_EMBLEM → bmw / M / alpina / rr // Startup animation (G)
- HMI_BRAND → BMW_M                      // M-style theme (G, i-Step ≥ 2019)
- BRAND → bmw / mini / rr / bmw_i        // Warning sounds (G)
```

---

## On-Screen Volume Bar

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- VOLUME_POPUP_DISPLAY → aktiv // Volume bar when adjusting (default: nicht_aktiv)
```

---

## Notes and Troubleshooting

| Problem / Error                   | How to check / Solution                                    |
| :-------------------------------- | :--------------------------------------------------------- |
| ASD does not work                 | Check that the ASD module exists, firmware version, engine |
| Startup animation does not change | Check STARTUP_EMBLEM + STARTUP_TYPE                        |
| Sound does not change             | Check SOUND_SIGNAL_SET, restart the head unit              |

---

> [!WARNING]
> ASD affects how the engine sound is perceived. Wrong Model Range / Engine
> values can produce an incorrect sound or an ASD module error.
