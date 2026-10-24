**English** | [Русский](E-Sys-Settings.ru.md)

# E-Sys Settings

> [!IMPORTANT]
> **E-Sys / E-Sys Launcher Pro** — the main software for FDL/VO coding of
> BMW F/G series.

---

## Required Settings

```text
Settings → Options → Update VCM... → OFF
Settings → Options → Update MSM... → OFF
```

> [!NOTE]
> Disabling VCM/MSM updates prevents accidentally overwriting the vehicle
> configuration when connecting.

---

## Data Paths

```text
Options → Paths:
- Data Directory:    C:\EC-Apps\ESys\data\
- Project Directory: C:\EC-Apps\ESys\projects\
```

---

## Interface Language

```text
Options → Language → English
```

> [!NOTE]
> The English interface is recommended for consistency with the
> documentation and the parameter names in E-Sys.

---

## Backup Before Coding

```text
1. Read the vehicle FA (Read FA)
2. Save the original parameters (Read Coding → Save)
3. Export the current SVT configuration
```

---

## E-Sys Quick Commands

| Action       | Command                          |
| :----------- | :------------------------------- |
| Connect      | Connection → Connect (**F3**)    |
| Disconnect   | Connection → Disconnect (**F4**) |
| Read coding  | Read Coding (**F5**)             |
| Write coding | Write Coding (**F6**)            |

> [!NOTE]
> Some functions (reading DME/DDE, flashing) are only available with the
> engine off and the ignition on.

---

## Notes and Troubleshooting

| Problem / Error  | How to check / Solution                 |
| :--------------- | :-------------------------------------- |
| Car not detected | Check ENET and ignition, wait 30 s      |
| Connection error | Restart E-Sys, reconnect the cable      |
| Wrong paths      | Set the Data/Project Directory manually |

---

> [!WARNING]
> Always connect a battery charger during long coding sessions. A voltage
> drop below 12 V can damage the ECUs.
