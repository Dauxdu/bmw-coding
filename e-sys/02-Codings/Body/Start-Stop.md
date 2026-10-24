**English** | [Русский](Start-Stop.ru.md)

# Start-Stop (MSA)

> [!IMPORTANT]
> **CAS, FEM_BODY, BDC_BODY, DME/DDE** — depending on the vehicle series.
> F01/F10 → CAS; F20/F30 → FEM_BODY; G-series → DME/DDE.

---

## Remember the Last Start-Stop Setting

### Parameter settings for F-series (F01, F10, F25)

```text
ECU: CAS → 3000
Parameters:
- TCM_MSA_MEMORY → aktiv // Remember the last state of the MSA button
```

### Parameter settings for F-series (F20, F30, F34)

```text
ECU: FEM_BODY → 3023
Parameters:
- TCM_MSA_MEMORY → aktiv // Remember the last state of the MSA button
```

### Parameter settings for G-series

```text
ECU: DME/DDE → 3000
Parameters:
- TCM_MSA_MEMORY → verbaut // Remember the last state (engine OFF, ignition ON)
```

> [!NOTE]
> The system remembers the last state of the Start-Stop button and
> restores it on the next engine start.

---

## Start-Stop Off by Default

### Parameter settings for F-series (F01, F10, F25)

```text
ECU: CAS → 3000
Parameters:
- TC_MSA_DEFAULT_OFF → aktiv // MSA off on every start
```

### Parameter settings for F-series (F20, F30, F34)

```text
ECU: FEM_BODY → 3023
Parameters:
- TCM_MSA_DEFAULT_OFF → aktiv // MSA off on every start
```

### Parameter settings for G-series

```text
ECU: DME/DDE → 3000
Parameters:
- TC_MSA_DEFAULT_OFF → verbaut // MSA off on every start
```

### Values

| State               | Value         |
| :------------------ | :------------ |
| Default (F-series)  | nicht_aktiv   |
| Default (G-series)  | nicht_verbaut |
| Modified (F-series) | aktiv         |
| Modified (G-series) | verbaut       |

---

## Eco Pro Does Not Enable Start-Stop

### Parameter settings for F-series

```text
ECU: FEM_BODY → 3023
Parameters:
- ECO_CONF_MSA → nicht_aktiv // Eco Pro mode does not activate MSA
```

### Parameter settings for G-series

```text
ECU: HU_MGU → 3008
Parameters:
- FES_ECO_CONF_MSA → nicht_aktiv // Eco Pro mode does not activate MSA
```

---

## Disabling the MSA Notification in the Instrument Cluster

### Parameter settings for F-series

```text
ECU: KOMBI → 3000
Parameters:
- MSA_VERFUEGBARANZEIGE_ENABLE → nicht_aktiv // Remove "Auto Start-Stop Off" from KOMBI
```

---

## Notes and Troubleshooting

| Problem / Error               | How to check / Solution                           |
| :---------------------------- | :------------------------------------------------ |
| Setting is not saved          | Check TCM_MSA_MEMORY, update the ECU firmware     |
| MSA behaves incorrectly       | Check the battery and sensors, run the adaptation |
| Error after coding a G-series | Make sure: engine OFF, ignition ON                |

---

> [!WARNING]
> On G-series, DME/DDE coding must be done strictly with the **engine off**
> and the **ignition on**. Breaking this order can damage the engine
> control unit.
