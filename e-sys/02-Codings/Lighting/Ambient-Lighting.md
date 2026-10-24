**English** | [Русский](Ambient-Lighting.ru.md)

# Ambient Lighting

> [!IMPORTANT]
> **FEM_BODY, BDC_BODY** — F-series → FEM_BODY; G-series → BDC_BODY.

---

## Ambient Lighting Brightness

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3070
Parameters:
- Ambiente_Helligkeit → user          // Lighting brightness (HEX, default: 64 = 100%)
- Ambiente_Nachfuehrung → nicht_aktiv // Decouple from KOMBI brightness (default: aktiv)
```

---

## Welcome Light Brightness

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3070
Parameters:
- WL_HELLIGKEIT → user // Welcome Light brightness (HEX, default: 64)
```

---

## Interior Light Duration on Lock/Unlock

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3070
Parameters:
- IB_Einschalt_begr_lok → user   // Light duration on lock (HEX seconds, default: 8)
- IB_Einschalt_begr_ulok → user  // Light duration on unlock (HEX seconds, default: 8)
```

---

## Door Handle Lights in Reverse Gear

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3070
Parameters:
- OVT_BEI_RUECKFAHRLICHT → aktiv // Door handle LEDs in reverse gear (default: nicht_aktiv)
```

> [!NOTE]
> On cars with a Top-View Camera this function is already active by default.

---

## Ambient Lighting Colors (G-series)

### Parameter settings for G-series

```text
ECU: BDC_BODY → 360A
Parameters:
- LIC_LCI_COLOR_LIBRARY_DATA → custom RGB // Custom interior lighting colors
```

### RGB values

| Color  | RGB (HEX)  |
| :----- | :--------- |
| White  | 90, E0, 90 |
| Bronze | D7, 6E, 14 |
| Orange | 93, 1A, 01 |
| Blue   | 00, 20, FE |
| Green  | 10, FE, 32 |
| Violet | 78, 3C, FE |

---

## Notes and Troubleshooting

| Problem / Error            | How to check / Solution                                    |
| :------------------------- | :--------------------------------------------------------- |
| Brightness does not change | Check Ambiente_Helligkeit and that ambient lighting exists |
| Lighting follows KOMBI     | Set Ambiente_Nachfuehrung → nicht_aktiv                    |
| Colors are not applied (G) | Check LIC_LCI_COLOR_LIBRARY_DATA and the BDC_BODY version  |

---

> [!WARNING]
> Changing the lighting colors on G-series requires a compatible BDC_BODY
> firmware version. Make a backup before changing them.
