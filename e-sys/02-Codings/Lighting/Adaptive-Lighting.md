**English** | [Русский](Adaptive-Lighting.ru.md)

# Adaptive Lighting (Cornering Lights)

> [!IMPORTANT]
> **FEM_BODY, FRM** — F-series → FEM_BODY; alternative via FRM.
> Requires front fog lights. Headlight mode: AUTO, at night.

---

## Adaptive Cornering Lights via the Fog Lights

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3073
Parameters:
- C_CLC_ENA → F030enable   // Enable cornering lights — Part 1 (default: F030disable)
- C_BLC_ENA → aktiv        // Enable cornering lights — Part 2 (default: nicht_aktiv)
- KL_ENABLE_RE → KL_Ein    // Enable cornering lights — Part 4 (default: KL_Aus)

ECU: FEM_BODY → 3066
Parameters:
- KL_ENABLE_LI → KL_Ein    // Enable cornering lights — Part 3 (default: KL_Aus)

ECU: FEM_BODY → 3062
Parameters:
- MAPPING_abbiegel_L_output → nsw_l // Map the left fog light to the cornering light (default: Off)
- MAPPING_abbiegel_R_output → nsw_r // Map the right fog light to the cornering light (default: Off)
```

> [!NOTE]
> When the steering wheel is turned at night (AUTO mode), the fog light on
> that side turns on to light up the turning area. All 6 parameters are
> required. Order: Part 1 → Part 2 → Part 3 → Part 4 → Part 5 → Part 6.

---

## Alternative Setup via FRM

### Parameter settings for F-series (F01, F10, F25)

```text
ECU: FRM
Parameters:
- Lamp_map_para_satz_01 → BV_F025_WERT02_Corneringlight-UBER-NSW
- Lamp_map_para_satz_02 → BV_F025_WERT02_Corneringlight-UBER-NSW
- ALC_AFS_ENABLE → aktiv
- U_EFF_CL → FF            // For LED headlights (or wert_07__13,0V = 82 for halogen)
```

---

## Notes and Troubleshooting

| Problem / Error                 | How to check / Solution                                           |
| :------------------------------ | :---------------------------------------------------------------- |
| Adaptive light does not turn on | Check the headlight mode (AUTO), time of day, the light sensor    |
| Only one side works             | Check MAPPING_abbiegel_L/R_output, the wiring, the fog light bulb |
| ECU error                       | Calibrate the headlights via service functions                    |

---

> [!WARNING]
> After changing lighting settings, it is recommended to run the headlight
> adaptation via a diagnostic scanner or the E-Sys service menu.
