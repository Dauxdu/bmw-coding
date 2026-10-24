**English** | [Русский](Instrument-Cluster.ru.md)

# Instrument Cluster (KOMBI)

> [!IMPORTANT]
> **KOMBI, DKOMBI4, ICM** — F-series → KOMBI; G-series → DKOMBI4.

---

## Digital Speedometer

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- BC_DIGITAL_V → aktiv // Current speed as digits in the BC list on the KOMBI display
```

### Parameter settings for G-series

```text
ECU: DKOMBI4 → 3000
Parameters:
- DIGIT_GESCHW_ENABLE → anzeige_kmh // Digital speed in the instrument cluster
- DIGIT_GESCHW_UPDATERATE → 2       // Speed refresh rate
```

---

## M Performance Logo on Startup

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- BMW_LOGO → mpm // M Performance logo (default: ag = Alpina)
```

### BMW_LOGO values

| Logo             | Value |
| :--------------- | :---- |
| Alpina (default) | ag    |
| M Performance    | mpm   |
| Standard BMW     | bmw   |

### Parameter settings for G-series

```text
ECU: DKOMBI4 → 3000
Parameters:
- GLOBAL_LAYOUT_VARIANTE → M / ALPINA / M_Performance // Instrument cluster layout
- LOGO_SCHRIFTZUG → msp_logo                          // M logo in Sport mode
- MPA_MSP_VIEW_ENABLE → grau_weiss                    // Grey color in Sport mode
```

---

## Disabling Speedometer Correction

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- BC_V_KORREKTUR → nicht_aktiv // Show the real speed without correction (default: aktiv)
```

> [!NOTE]
> With the correction disabled, the speedometer will read ~2 km/h below
> the set cruise control speed.

---

## Trip Computer Auto-Reset

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- BC_AUTORESET_ZEIT → werte=04 // Trip computer auto-reset (HEX hours, default: 04 = 4 hours, FF = never)
```

---

## White KOMBI Backlight at Night

### Parameter settings for F-series

```text
ECU: KOMBI → 3007
Parameters:
- DIM_NACHT_EIN → werte=FF // White backlight at night (default: 32 = orange)
```

---

## Sport+ Icon on KOMBI

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- FDS_MENUE_TEXT_1 → menue_3   // Sport+ icon (default: menue_4)
- FDS_MENUE_TEXT_2 → menue_3
- FDS_MENUE_TEXT_3 → menue_3
- FDS_MENUE_TEXT_4 → menue_3
- FDS_MENUE_SIGNAL_1 → menue_3 // Sport+ signal (default: menue_4)
- FDS_MENUE_SIGNAL_2 → menue_3
- FDS_MENUE_SIGNAL_3 → menue_3
- FDS_MENUE_SIGNAL_4 → menue_3
```

---

## LIM Function (Speed Limiter)

### Parameter settings for F-series

```text
ECU: KOMBI → 3003
Parameters:
- SLD_ENABLE → aktiv // LIM function — Part 1

ECU: ICM → 3000
Parameters:
- SLD_Funktion → aktiv                    // LIM function — Part 2
- C_Umschaltung_ACC_DCC → zugelassen      // LIM function — Part 3 (default: unterdruecken)
- LDM_SET_Taste → nur_SET__O              // LIM function — Part 4 (default: SET_und_aktivieren__IO)
```

> [!NOTE]
> The cruise control "Set" button starts working as the "LIM" button
> (speed limiter). All 4 parameters are required.

---

## Disabling the MSA Notification on KOMBI

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- MSA_VERFUEGBARANZEIGE_ENABLE → nicht_aktiv // Remove "Auto Start-Stop Off" (default: aktiv)
```

---

## Disabling the Reverse Gear Chime

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- R_GANG_AKUSTIK_ENABLE → nicht_aktiv // Remove the chime when R is engaged (default: aktiv)
```

---

## Notes and Troubleshooting

| Problem / Error               | How to check / Solution                                             |
| :---------------------------- | :------------------------------------------------------------------ |
| Digital speedometer not shown | Check BC_DIGITAL_V and the KOMBI firmware version                   |
| Logo does not change          | Make sure the mpm/ag value is supported by your KOMBI version       |
| LIM does not work             | Check all 4 parameters (KOMBI + ICM) and that cruise control exists |

---

> [!WARNING]
> Do not cut the power while coding KOMBI. Use a stable voltage (connect a
> charger). Back up the original coding before writing.
