# BMW ENET Coding Guide

Комплексное руководство по кодированию BMW F/G серий через ENET.

> [!WARNING]
> Используйте на свой страх и риск. Автор не несет ответственности за любые повреждения вашего автомобиля. Всегда делайте резервные копии перед внесением изменений.

---

## Требования

1. **ENET кабель** для подключения к автомобилю
2. **E-Sys** программное обеспечение для F/G серий
3. **ISTA+/Rheingold** для диагностики (опционально)

---

## Быстрый старт

### Подключение через ENET

1. Установите драйверы для ENET кабеля
2. Запустите E-Sys
3. Подключитесь к автомобилю
4. Выберите нужный модуль для кодирования

---

## Структура репозитория

### 01 - Setup

- [E-Sys Settings](01-Setup/E-Sys-Settings.md) — настройки программы
- [ENET Connection](01-Setup/ENET-Connection.md) — порядок подключения к автомобилю

### 02 - Codings

**Body**

- [Mirrors](02-Codings/Body/Mirrors.md) — зеркала, парковочный наклон
- [Start-Stop](02-Codings/Body/Start-Stop.md) — отключение, память, поведение по умолчанию
- [Trunk (HKL)](02-Codings/Body/Trunk-HKL.md) — плавное открытие/закрытие, комфорт-доступ
- [Windows & Doors](02-Codings/Body/Windows-Doors.md) — стеклоподъёмники, блокировка при открытии двери

**Driver Assistance**

- [FCW (Collision Warning)](02-Codings/Driver-Assistance/FCW.md) — предупреждение о столкновении
- [LDW (Lane Departure)](02-Codings/Driver-Assistance/LDW.md) — контроль полосы, пороги срабатывания
- [Traffic Sign Recognition](02-Codings/Driver-Assistance/Traffic-Sign.md) — чтение дорожных знаков

**Head Unit**

- [CarPlay](02-Codings/Head-Unit/CarPlay.md) — активация и настройки
- [Codecs & USB Video](02-Codings/Head-Unit/Codecs-USB-Video.md) — поддержка форматов видео
- [HUD](02-Codings/Head-Unit/HUD.md) — проекционный дисплей, поворотники, настройки
- [Radio Settings](02-Codings/Head-Unit/Radio-Settings.md) — регион, частоты, отображение
- [Video in Motion](02-Codings/Head-Unit/Video-in-Motion.md) — видео на ходу, разблокировка

**Lighting**

- [Adaptive Lighting](02-Codings/Lighting/Adaptive-Lighting.md) — поворотный свет, угол наклона
- [Daytime Running Lights](02-Codings/Lighting/Daytime-Running-Lights.md) — ДХО, яркость, управление
- [Fog Lights](02-Codings/Lighting/Fog-Lights.md) — ПТФ: стробоскоп, адаптивное освещение
- [High Beam Assistant](02-Codings/Lighting/High-Beam-Assistant.md) — автоматический дальний свет
- [Turn Signals](02-Codings/Lighting/Turn-Signals.md) — поворотники, нефиксируемые, дублирование в HUD

**Transmission**

- [Paddle Shifters](02-Codings/Transmission/Paddle-Shifters.md) — лепестки переключения, ручной режим
- [Sport Mode](02-Codings/Transmission/Sport-Mode.md) — Sport+, Comfort+, режимы АКПП

**Instrument Cluster**

- [Instrument Cluster](02-Codings/Instrument-Cluster.md) — цифровой спидометр, логотипы, индикация

### 03 - Features

- [Comfort Features](03-Features/Comfort-Features.md) — комфортные функции
- [Sport Features](03-Features/Sport-Features.md) — спортивные режимы и настройки
- [Safety Features](03-Features/Safety-Features.md) — безопасность и ассистенты

### 04 - Reference

- [Service Intervals (FA Codes)](04-Reference/Service-Intervals.md) — интервалы ТО
- [Vehicle Series Codes](04-Reference/Vehicle-Series-Codes.md) — коды серий и моделей
