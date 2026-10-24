[English](HUD.md) | **Русский**

# HUD (Head-Up Display)

> [!IMPORTANT]
> **KOMBI, HU_NBT, HU_CIC** — параметры HUD находятся в KOMBI и HU,
> а не в отдельном модуле «HUD».

---

## Отображение развязок на HUD

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3000
Параметры:
- JUNCTION_VIEW_HUD → aktiv // Изображения развязок на HUD (default: nicht_aktiv)
```

---

## Дистанция ACC (iBrake) в HUD

### Настройка параметров для F-серии

```text
Блок: HU_CIC → 3000
Параметры:
- HUD_DISTANCE_INFO → aktiv // Дистанция ACC в HUD — Part 1

Блок: KOMBI → 3008
Параметры:
- HUD_PIA_IBRAKE → aktiv // Дистанция ACC в HUD — Part 2

Блок: KOMBI → 3000
Параметры:
- IBRAKE_ABSTAND_ENABLE → aktiv // Дистанция ACC в HUD — Part 3
```

---

## Развлечения и телефон в HUD

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- HUD_ENTERTAINMENT_ENABLE → aktiv   // Меню развлечений в HUD
- HUD_TELEFONANRUF_ENABLE → aktiv    // Список звонков в HUD
- HUD_SPRACHEINGABE_ENABLE → aktiv   // Голосовые команды в HUD
```

### Настройка параметров для F-серии (HU_CIC)

```text
Блок: HU_CIC → 3000
Параметры:
- HUD_ENTERTAINMENTLIST → aktiv // Чекбокс «Entertainment/Telephone» в настройках HUD
```

---

## Время заставки HUD

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- HUD_START_UP_SCREEN_ANZ_ZEIT → user // Время заставки HUD в секундах (default: 3)
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка        | Как проверить настройку / Решение                     |
| :----------------------- | :---------------------------------------------------- |
| HUD не включается        | Проверить питание, наличие опции HUD, версию прошивки |
| Изображение размыто      | Откалибровать положение и фокус через сервисное меню  |
| Развязки не отображаются | Проверить JUNCTION_VIEW_HUD, обновление карт          |

---

> [!WARNING]
> Большинство функций HUD уже активны на F30/F32 2013+. Перед
> кодированием проверьте текущие значения параметров.
