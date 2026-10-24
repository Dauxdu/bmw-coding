[English](README.md) | **Русский**

# E-Sys — FDL/VO-кодирование

[← На главную](../README.ru.md)

## Быстрый старт

```text
1. Подключить ENET к OBD-II
2. Включить зажигание, подождать 30 сек
3. E-Sys → Connection → Connect (F3)
4. Выбрать Target Series (например, F020 для F30)
5. Read SVT → Выбрать ECU → Read Coding (F5)
6. Изменить FDL-параметры → Write Coding (F6)
```

---

## 01 — Setup

- [ENET Connection](../ENET-Connection.ru.md)
- [E-Sys Settings](01-Setup/E-Sys-Settings.ru.md)

## 02 — Codings

**Body**

- [Mirrors](02-Codings/Body/Mirrors.ru.md)
- [Start-Stop](02-Codings/Body/Start-Stop.ru.md)
- [Trunk (HKL)](02-Codings/Body/Trunk-HKL.ru.md)
- [Windows & Doors](02-Codings/Body/Windows-Doors.ru.md)
- [Headlamp Washers](02-Codings/Body/Headlamp-Washers.ru.md)

**Driver Assistance**

- [FCW](02-Codings/Driver-Assistance/FCW.ru.md)
- [LDW](02-Codings/Driver-Assistance/LDW.ru.md)
- [Traffic Sign](02-Codings/Driver-Assistance/Traffic-Sign.ru.md)

**Head Unit**

- [CarPlay](02-Codings/Head-Unit/CarPlay.ru.md)
- [Codecs & USB Video](02-Codings/Head-Unit/Codecs-USB-Video.ru.md)
- [HUD](02-Codings/Head-Unit/HUD.ru.md)
- [iDrive Features](02-Codings/Head-Unit/iDrive-Features.ru.md)
- [Radio Settings](02-Codings/Head-Unit/Radio-Settings.ru.md)
- [Video in Motion](02-Codings/Head-Unit/Video-in-Motion.ru.md)

**Lighting**

- [Adaptive Lighting](02-Codings/Lighting/Adaptive-Lighting.ru.md)
- [Ambient Lighting](02-Codings/Lighting/Ambient-Lighting.ru.md)
- [Daytime Running Lights](02-Codings/Lighting/Daytime-Running-Lights.ru.md)
- [Exterior Lights](02-Codings/Lighting/Exterior-Lights.ru.md)
- [Fog Lights](02-Codings/Lighting/Fog-Lights.ru.md)
- [High Beam Assistant](02-Codings/Lighting/High-Beam-Assistant.ru.md)
- [Turn Signals](02-Codings/Lighting/Turn-Signals.ru.md)

**Transmission**

- [Paddle Shifters](02-Codings/Transmission/Paddle-Shifters.ru.md)
- [Sport Mode](02-Codings/Transmission/Sport-Mode.ru.md)

**Instrument Cluster**

- [Instrument Cluster](02-Codings/Instrument-Cluster.ru.md)

## 03 — Features

- [Comfort Features](03-Features/Comfort-Features.ru.md)
- [Safety Features](03-Features/Safety-Features.ru.md)
- [Sport Features](03-Features/Sport-Features.ru.md)

## 04 — Reference

- [Service Intervals](04-Reference/Service-Intervals.ru.md)
- [Vehicle Series Codes](04-Reference/Vehicle-Series-Codes.ru.md)

---

## Поддерживаемые кузова

| Платформа | Модели                                                      |
| :-------- | :---------------------------------------------------------- |
| F001      | F01, F02, F03, F04, F07, RR                                 |
| F010      | F05, F06, F10, F11, F12, F13, F18                           |
| F020      | F20, F21, F22, **F30**, F31, F32, F33, F34, F35, F36, M3/M4 |
| F025      | F15, F16, F25, F26, X5M, X6M                                |
| F056      | F39, F45, F46, F47, F48, F54, F55, F56, F57, F60            |
| S15A      | G01, G02, G11, G12, **G30**, G31, G32                       |
| S18A      | **G20**, G21, G22, G23, G26, G28, G29, G42, G80, G82, G83   |

---

## Основные блоки ECU

| ECU             | Назначение                          |
| :-------------- | :---------------------------------- |
| FEM_BODY        | Кузов, освещение, стёкла (F-series) |
| BDC_BODY        | Кузов, освещение, стёкла (G-series) |
| REM             | Задние фонари, стёкла               |
| KOMBI / DKOMBI4 | Приборная панель, HUD               |
| HU_NBT / HU_MGU | iDrive, мультимедиа, навигация      |
| KAFAS2 / KAFAS  | Камера: FCW, LDW, знаки, HBA        |
| ICM             | Режимы вождения, ACC                |
| EGS             | Логика АКПП, лепестки               |
| DME / DDE       | Двигатель, MSA (G-series)           |
| IHKA            | Климат-контроль                     |
| ACSM            | Ремни, подушки безопасности         |
| HKFM / HKL      | Привод багажника                    |
| ASD             | Active Sound Design                 |
| SM2             | Сиденья, Easy Entry                 |
