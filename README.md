# BMW ENET Coding Guide

Комплексное руководство по кодированию BMW F/G серий через ENET.

> [!WARNING]
> **DISCLAIMER / ОТКАЗ ОТ ОТВЕТСТВЕННОСТИ**
>
> Все кодировки вы выполняете на свой страх и риск. Автор не несёт
> ответственности за повреждение электронных блоков, потерю гарантии
> или нарушение ПДД. Всегда делайте резервную копию (Read Coding)
> перед записью. Некоторые изменения могут быть незаконны в вашей стране.

---

## Требования

1. **ENET-кабель** (OBD-II → RJ45)
2. **E-Sys** / E-Sys Launcher Pro / BimmerCode
3. **ISTA+/Rheingold** для диагностики (опционально)
4. Зарядное устройство АКБ (≥ 12.5 В)

---

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

## Структура репозитория

### 01 — Setup

- [ENET Connection](01-Setup/ENET-Connection.md)
- [E-Sys Settings](01-Setup/E-Sys-Settings.md)

### 02 — Codings

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
- [Fog Lights](02-Codings/Lighting/Fog-Lights.md)
- [High Beam Assistant](02-Codings/Lighting/High-Beam-Assistant.md)
- [Turn Signals](02-Codings/Lighting/Turn-Signals.md)

**Transmission**

- [Paddle Shifters](02-Codings/Transmission/Paddle-Shifters.md)
- [Sport Mode](02-Codings/Transmission/Sport-Mode.md)

**Instrument Cluster**

- [Instrument Cluster](02-Codings/Instrument-Cluster.md)

### 03 — Features

- [Comfort Features](03-Features/Comfort-Features.md)
- [Safety Features](03-Features/Safety-Features.md)
- [Sport Features](03-Features/Sport-Features.md)

### 04 — Reference

- [Service Intervals](04-Reference/Service-Intervals.md)
- [Vehicle Series Codes](04-Reference/Vehicle-Series-Codes.md)

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

---

## Правила безопасности

1. **Всегда backup** — Read Coding перед любой записью
2. **Стабильное питание** — ЗУ на АКБ (≥ 12.5 В)
3. **Не отключать ENET** во время чтения/записи
4. **Одно изменение за раз** — тестировать после каждого
5. **VO перед FDL** — VO Coding сбрасывает FDL до default
