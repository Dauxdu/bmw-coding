**English** | [Русский](README.ru.md)

# E-Sys — FDL/VO Coding

[← Back to main page](../README.md)

## Quick Start

```text
1. Connect ENET to OBD-II
2. Switch on the ignition, wait 30 s
3. E-Sys → Connection → Connect (F3)
4. Select the Target Series (e.g. F020 for the F30)
5. Read SVT → select the ECU → Read Coding (F5)
6. Change the FDL parameters → Write Coding (F6)
```

---

## 01 — Setup

- [ENET Connection](../ENET-Connection.md)
- [E-Sys Settings](01-Setup/E-Sys-Settings.md)

## 02 — Codings

**Body**

- [Mirrors](02-Codings/Body/Mirrors.md)
- [Start-Stop](02-Codings/Body/Start-Stop.md)
- [Trunk (HKL)](02-Codings/Body/Trunk-HKL.md)
- [Windows & Doors](02-Codings/Body/Windows-Doors.md)
- [Headlamp Washers](02-Codings/Body/Headlamp-Washers.md)

**Driver Assistance**

- [FCW](02-Codings/Driver-Assistance/FCW.md)
- [LDW](02-Codings/Driver-Assistance/LDW.md)
- [Traffic Sign](02-Codings/Driver-Assistance/Traffic-Sign.md)

**Head Unit**

- [CarPlay](02-Codings/Head-Unit/CarPlay.md)
- [Codecs & USB Video](02-Codings/Head-Unit/Codecs-USB-Video.md)
- [HUD](02-Codings/Head-Unit/HUD.md)
- [iDrive Features](02-Codings/Head-Unit/iDrive-Features.md)
- [Radio Settings](02-Codings/Head-Unit/Radio-Settings.md)
- [Video in Motion](02-Codings/Head-Unit/Video-in-Motion.md)

**Lighting**

- [Adaptive Lighting](02-Codings/Lighting/Adaptive-Lighting.md)
- [Ambient Lighting](02-Codings/Lighting/Ambient-Lighting.md)
- [Daytime Running Lights](02-Codings/Lighting/Daytime-Running-Lights.md)
- [Exterior Lights](02-Codings/Lighting/Exterior-Lights.md)
- [Fog Lights](02-Codings/Lighting/Fog-Lights.md)
- [High Beam Assistant](02-Codings/Lighting/High-Beam-Assistant.md)
- [Turn Signals](02-Codings/Lighting/Turn-Signals.md)

**Transmission**

- [Paddle Shifters](02-Codings/Transmission/Paddle-Shifters.md)
- [Sport Mode](02-Codings/Transmission/Sport-Mode.md)

**Instrument Cluster**

- [Instrument Cluster](02-Codings/Instrument-Cluster.md)

## 03 — Features

- [Comfort Features](03-Features/Comfort-Features.md)
- [Safety Features](03-Features/Safety-Features.md)
- [Sport Features](03-Features/Sport-Features.md)

## 04 — Reference

- [Service Intervals](04-Reference/Service-Intervals.md)
- [Vehicle Series Codes](04-Reference/Vehicle-Series-Codes.md)

---

## Supported Platforms

| Platform | Models                                                      |
| :------- | :---------------------------------------------------------- |
| F001     | F01, F02, F03, F04, F07, RR                                 |
| F010     | F05, F06, F10, F11, F12, F13, F18                           |
| F020     | F20, F21, F22, **F30**, F31, F32, F33, F34, F35, F36, M3/M4 |
| F025     | F15, F16, F25, F26, X5M, X6M                                |
| F056     | F39, F45, F46, F47, F48, F54, F55, F56, F57, F60            |
| S15A     | G01, G02, G11, G12, **G30**, G31, G32                       |
| S18A     | **G20**, G21, G22, G23, G26, G28, G29, G42, G80, G82, G83   |

---

## Main ECUs

| ECU             | Purpose                            |
| :-------------- | :--------------------------------- |
| FEM_BODY        | Body, lighting, windows (F-series) |
| BDC_BODY        | Body, lighting, windows (G-series) |
| REM             | Tail lights, windows               |
| KOMBI / DKOMBI4 | Instrument cluster, HUD            |
| HU_NBT / HU_MGU | iDrive, multimedia, navigation     |
| KAFAS2 / KAFAS  | Camera: FCW, LDW, signs, HBA       |
| ICM             | Driving modes, ACC                 |
| EGS             | Transmission logic, paddles        |
| DME / DDE       | Engine, MSA (G-series)             |
| IHKA            | Climate control                    |
| ACSM            | Seat belts, airbags                |
| HKFM / HKL      | Tailgate drive                     |
| ASD             | Active Sound Design                |
| SM2             | Seats, Easy Entry                  |
