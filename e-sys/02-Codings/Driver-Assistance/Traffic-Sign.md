**English** | [Русский](Traffic-Sign.ru.md)

# Traffic Sign Recognition

> [!IMPORTANT]
> **KAFAS2, KOMBI, HUD** — KAFAS2 = recognition camera;
> KOMBI/HUD = sign display.

---

## Setting the Recognition Region

### Parameter settings for F-series

```text
ECU: KAFAS2 → 3000
Parameters:
- COUNTRY_VARIATION → ECE                // Camera region (default: market-dependent, USA = 03)
- TSM_COUNTRY_VARIATION → ECE            // Sign recognition region (default: market-dependent, USA = 02)
- COD_CAM_ONLY → fusion_mode             // Camera + navigation data (default: fusion_mode = 01)
- COUNTRY_CODING_DISPLAY → country_specific // Country-specific sign display (default: country_specific = 02)
```

> [!NOTE]
> `ECE` is the European road sign standard (also applies to Russia/CIS).

---

## Notes and Troubleshooting

| Problem / Error          | How to check / Solution                                                  |
| :----------------------- | :----------------------------------------------------------------------- |
| Signs are not recognized | Check COUNTRY_VARIATION, TSM_COUNTRY_VARIATION, that the camera is clean |
| Wrong signs              | Make sure the correct region (e.g. ECE) is set in both parameters        |
| Signs are not displayed  | Check the parameters in KOMBI/HUD                                        |

---

> [!WARNING]
> Sign recognition only works with good visibility and a clean windshield
> in the camera area. It may not recognize temporary or non-standard signs.
