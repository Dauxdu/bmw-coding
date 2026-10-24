**English** | [Русский](README.ru.md)

# BMW ENET Coding Guide

A comprehensive guide to coding and servicing BMW F/G series via ENET.

> [!WARNING]
> **DISCLAIMER**
>
> You perform all codings at your own risk. The author is not responsible
> for damaged ECUs, loss of warranty or traffic law violations. Always make
> a backup (Read Coding) before writing. Some changes may be illegal in
> your country. See [DISCLAIMER](DISCLAIMER.md).

---

## Choose Your Tool

| Section                    | What it is for                                         |
| :------------------------- | :----------------------------------------------------- |
| **[E-Sys](e-sys/README.md)** | FDL/VO coding: lighting, iDrive, comfort, driving modes |
| **[ISTA+](ista+/README.md)** | Diagnostics and service functions                    |

Shared for both: [ENET Connection](ENET-Connection.md)

---

## Requirements

1. **ENET cable** (OBD-II → RJ45)
2. **E-Sys** / E-Sys Launcher Pro / BimmerCode — for coding
3. **ISTA+/Rheingold** — for diagnostics and service functions
4. Battery charger (≥ 12.5 V)

---

## Safety Rules

1. **Always back up** — Read Coding before any write
2. **Stable power** — charger on the battery (≥ 12.5 V)
3. **Do not disconnect ENET** during read/write
4. **One change at a time** — test after each one
5. **VO before FDL** — VO coding resets FDL to default

---

## Languages

Every page exists in English (`Name.md`) and Russian (`Name.ru.md`);
use the switch at the top of each page. See [CONTRIBUTING](CONTRIBUTING.md).
