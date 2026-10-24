**English** | [Русский](Fog-Lights.ru.md)

# Fog Lights

> [!IMPORTANT]
> **FEM_BODY, FRM, BDC_BODY** — F-series → FEM_BODY; G-series → BDC_BODY.
> Requires front fog lights.

---

## Fog Lights Stay On with High Beams

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3050
Parameters:
- NSW_AUS_BEI_FL → nicht_aktiv // Fog lights do NOT turn off with high beams (default: aktiv)
```

### Parameter settings for G-series

```text
ECU: BDC_BODY → 7083
Parameters:
- NSW_AUS_BEI_FL → nicht_aktiv // Fog lights do NOT turn off with high beams
```

### Values

| Behavior                                 | Value       |
| :--------------------------------------- | :---------- |
| Fog lights off with high beams (default) | aktiv       |
| Fog lights stay on with high beams       | nicht_aktiv |

> [!NOTE]
> By default (aktiv), the fog lights turn off when the high beams are
> switched on. The value `nicht_aktiv` keeps the fog lights on, creating a
> strobe effect when switching.

---

## Fog Lights with Position Lights

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- NSW_EIN_AUF_LDS_STL → aktiv // Fog lights turn on in the "position lights" switch position (default: nicht_aktiv)
```

---

## Fog Lights in the Welcome Light

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3063
Parameters:
- MAPPING_NEBELSCHW_L_PART_OF_WL → Soft_On // Left fog light in the Welcome Light
- MAPPING_NEBELSCHW_R_PART_OF_WL → Soft_On // Right fog light in the Welcome Light
```

> [!NOTE]
> When the car is unlocked, the fog lights fade in together with the
> other Welcome Light elements.

---

## Rear Fog Lights

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3060
Parameters:
- NSL_Verbaut → Verbaut // Rear fog light button — Part 1 (default: nicht_verbaut)

ECU: REM → 3063
Parameters:
- Mapping_Nebelschlussl_L_output → nsl_l               // Rear left — Part 2 (default: off)
- Mapping_Nebelschlussl_L_Function → nebelschlusslicht // Rear left — Part 3
- Mapping_Nebelschlussl_R_output → nsl_r               // Rear right — Part 4 (default: off)
- Mapping_Nebelschlussl_R_Function → nebelschlusslicht // Rear right — Part 5
```

> [!NOTE]
> Requires a working rear fog light button on the light switch module.

---

## Notes and Troubleshooting

| Problem / Error                                | How to check / Solution                           |
| :--------------------------------------------- | :------------------------------------------------ |
| Fog lights do (not) turn off with high beams   | Check NSW_AUS_BEI_FL and the light sensor status  |
| Fog lights do not turn on with position lights | Check NSW_EIN_AUF_LDS_STL and the switch position |
| ECU error                                      | Reset the lighting adaptations                    |

---

> [!WARNING]
> In some regions, using fog lights together with high beams is prohibited
> by traffic law. Check your local legislation.
