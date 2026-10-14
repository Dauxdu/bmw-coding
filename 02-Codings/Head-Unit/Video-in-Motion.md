# Video in Motion

> [!IMPORTANT]
> **HU_NBT, HU_CIC** — HU_ENTRY не поддерживает Video in Motion.
> G-series → HU_NBT_EVO / HU_MGU.

---

## Базовая разблокировка видео на ходу

### Настройка параметров для F-серии (HU_NBT)

```text
Блок: HU_NBT → 3000
Параметры:
- SPEEDLOCK_X_KMH_MIN → werte=FF               // Снять блокировку видео (мин. скорость)
- SPEEDLOCK_X_KMH_MAX → werte=FF               // Снять блокировку видео (макс. скорость)
- VIDEO_HANDBRAKE → nicht_aktiv                // Убрать требование ручника
- VIDEO_FRONT_LOCKED → nicht_aktiv             // Убрать Front Lock
- VIDEO_SPEEDLOCK_CONDITION → none             // Убрать условие скорости
- SPEEDLOCK_FREISCHALTMENU → aktiv             // Меню разблокировки в Media
- SERVICES_MESSAGES_SPEEDLOCK_CONDITION → none // Сообщения сервисов на ходу
- OFFICE_MESSAGES_SPEEDLOCK_CONDITION → none   // Офисные сообщения на ходу
```

### Настройка параметров для F-серии (HU_CIC)

```text
Блок: HU_CIC → 3000
Параметры:
- SPEEDLOCK_X_KMH_MIN → werte=FF         // Снять блокировку видео (мин)
- SPEEDLOCK_X_KMH_MAX → werte=FF         // Снять блокировку видео (макс)
- VIDEO_NUR_MIT_HANDBREMSE → nicht_aktiv // Убрать требование ручника
```

### Настройка параметров для G-серии

```text
Блок: HU_NBT_EVO → 3000
Параметры:
- SPEEDLOCK_SPEEDVALUE_MIN → werte=1F   // Снять блокировку (G)
- SPEEDLOCK_SPEEDVALUE_MAX → werte=3F   // Снять блокировку (G)
- SPEEDLOCK_FREISCHALTMENU → aktiv      // Меню разблокировки (G)
```

---

## Альтернативный метод через меню (NBT)

```text
1. Толкнуть шайбу iDrive вверх (удерживать)
2. Перейти: Media → Menu → Media → CD/MM
3. Deactivate Speedlock → Yes
```

> [!NOTE]
> Требует предварительной активации `SPEEDLOCK_FREISCHALTMENU → aktiv`.

---

## Owner's Manual in Motion

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3000
Параметры:
- SL06_IBA_1 → nicht_aktiv // Руководство на ходу — Part 1 (default: aktiv)
- SL07_IBA_2 → nicht_aktiv // Руководство на ходу — Part 2 (default: aktiv)
- SL21_IBA_3 → nicht_aktiv // Руководство на ходу — Part 3 (default: aktiv)
```

---

## Камера в движении

### Настройка параметров для F-серии

```text
Блок: REM/PMA
Параметры:
- V_SCHWELLE_1 → werte=FF // Скорость отключения верхней камеры (FF = 255 км/ч, default: 24)
- V_SCHWELLE_2 → werte=FF // Скорость отключения задней камеры (FF = 255 км/ч, default: 0F)
- D_SCHWELLE_1 → werte=FF // Дистанция отключения верхней камеры (FF = 255 м, default: 32)
- D_SCHWELLE_2 → werte=FF // Дистанция отключения задней камеры (FF = 255 м, default: 0A)

Блок: TRSVC → 3000
Параметры:
- SV_Activate_Speed_Limit → werte=FF   // Боковая камера на любой скорости — Part 1
- SV_Deactivate_Speed_Limit → werte=FF // Боковая камера на любой скорости — Part 2
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка                | Как проверить настройку / Решение                   |
| :------------------------------- | :-------------------------------------------------- |
| Видео всё ещё блокируется        | Проверить все параметры SPEEDLOCK, перезагрузить ГУ |
| Чёрный экран при воспроизведении | Проверить формат видео, кодек, разрешение           |
| Камера отключается на скорости   | Проверить V_SCHWELLE_1/2, D_SCHWELLE_1/2 в REM/PMA  |

---

> [!WARNING]
> Просмотр видео водителем во время движения запрещён ПДД в
> большинстве стран. Используйте функцию только для пассажиров.
