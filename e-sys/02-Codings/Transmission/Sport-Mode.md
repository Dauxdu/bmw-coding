**English** | [Русский](Sport-Mode.ru.md)

# Sport Mode & Driving Modes

> [!IMPORTANT]
> **ICM, EGS, DME/DDE, HU_NBT, BDC_BODY, HU_MGU** — F-series → ICM + EGS;
> G-series → BDC_BODY + HU_MGU.

---

## Sport Auto Transmission

### VO coding for F-series

```text
1. Open the vehicle FA in E-Sys
2. Change option 205 → 2TB
3. Click "Calculate FP"
4. Code the ECUs: EGS, ICM, KOMBI
```

### Parameter settings for F-series

```text
ECU: ICM → 3000
Parameters:
- IcmKod_B_S2TBA → verbaut               // Sport automatic transmission logic (default: nicht_verbaut)
- ICMKOD_B_SPORTLENKUNG → aktiv          // Sport+ mode (default: nicht_aktiv)
- ICMKOD_B_InitEco → verbaut             // Eco Pro by default on start (default: nicht_verbaut)
- ICMKOD_B_SPORTINDIVIDUALISIERBAR → ein // Sport configuration in iDrive — Part 2 (default: aus)
- C_Abstandsstufe_init → Stufe_1         // Minimum ACC distance on start (default: Stufe_4)

ECU: EGS → 3000
Parameters:
- Sportschalter → aktiv      // Sport shift logic
- Sportschalter_alt → aktiv  // Sport shift logic (alternative)
- Applikation_LC → aktiv     // Launch Control (requires 2TB in the FA)
```

### Parameter settings for G-series

```text
ECU: BDC_BODY → 3221
Parameters:
- FesSportWorldMode1 → SportExpert     // Sport+ mode (G)
- FesComfortWorldMode1 → ComfortPlus   // Comfort+ mode (G)
- FesEcoWorldMode1 → ecoproplus        // Eco Pro+ mode (G)
- FesPiaDefaultLastUserMode → 04       // Default mode (01=Sport, 04=Comfort, 07=EcoPro)

ECU: HU_MGU → 3000
Parameters:
- FES_SPORT_EXPERT → aktiv   // Sport+ menu item (G)
- FES_COMFORT_PLUS → aktiv   // Comfort+ menu item (G)
- FES_ECO_PLUS → aktiv       // Eco Pro+ menu item (G)
```

> [!NOTE]
> Sport Auto Transmission provides later upshifts, earlier downshifts and
> a more aggressive throttle response. It also activates Sport+ mode.

---

## Sport Configuration in iDrive

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- Macro_fds → popup_and_config // Sport mode configuration in iDrive (default: popup_only)
```

---

## Disabling Regenerative Charging (IGR)

### Parameter settings for F-series

```text
ECU: DME → 3000
Parameters:
- IGR → werte=00 // Regeneration off, battery charges to 100% (default: ~80%)
```

> [!NOTE]
> By default the battery is charged to ~80%, leaving 20% for regeneration.
> Disabling it = charging to 100%, but about +3% fuel consumption.

---

## Coasting in Eco Pro (Segeln / Sailing)

### Parameter settings for F-series

```text
ECU: FEM_BODY
Parameters:
- SEGELN_ENABLE → aktiv // Coasting — Part 1

ECU: HU_NBT
Parameters:
- EFF_DYN_SAILING → aktiv // Coasting — Part 2 (item in the Eco Pro settings)

ECU: ICM
Parameters:
- C_Segeln_vorhanden → enable // Coasting — Part 3

ECU: EGS
Parameters:
- Segeln → aktiv // Coasting — Part 4
```

> [!NOTE]
> Automatic transmission only. Code all 4 ECUs. In Eco Pro, when you lift
> off the throttle at ~50–160 km/h, the transmission disengages and the car
> coasts.

---

## Sport Displays (HU_CIC)

### Parameter settings for F-series (without navigation)

```text
ECU: HU_CIC → 3000
Parameters:
- EFF_DYN_SPORT_CID → aktiv  // Sport displays in iDrive without navigation
- EFF_DYN_SPORT_UNIT → aktiv // Units in the sport displays
```

---

## Notes and Troubleshooting

| Problem / Error              | How to check / Solution                                        |
| :--------------------------- | :------------------------------------------------------------- |
| Modes do not switch          | Check the button, ICMKOD_B_SPORTLENKUNG, firmware version      |
| Transmission logic unchanged | Make sure ICM + EGS are coded, run the transmission adaptation |
| Launch Control does not work | Check Applikation_LC and that 2TB is in the FA                 |

---

> [!WARNING]
> After changing transmission settings, it is recommended to run the
> transmission adaptation via E-Sys service functions. VO coding (2TB)
> resets the FDL values in EGS, ICM and KOMBI to factory defaults.
