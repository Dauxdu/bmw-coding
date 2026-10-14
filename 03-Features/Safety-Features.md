# Safety Features

> [!IMPORTANT]
> **ACSM, ICM, KAFAS, HU_NBT, BDC_BODY** — ACSM = модуль безопасности;
> ICM = шасси; KAFAS = камера.

---

## Отключение напоминания о ремне безопасности

### Настройка параметров для F-серии

```text
Блок: ACSM → 3000
Параметры:
- SeatBeltReminder_SBR_Fahrer → nicht_aktiv              // Напоминание водителя (default: aktiv)
- SeatBeltReminder_SBR_Beifahrer → nicht_aktiv           // Напоминание пассажира (default: aktiv)
- SBR_FA_GWF_SBR_FA → nicht_aktiv                        // Напоминание водителя (альт.)
- SBR_BF_GWF_SBR_BF → nicht_aktiv                        // Напоминание пассажира (альт.)
- Initialwarnung_GWF_IW → nicht_aktiv                    // Гонг при запуске (default: aktiv)
- Gurtzustandsanzeige_Fahrer_GWF_GZA_FA → nicht_aktiv    // Значок ремня водителя
- Gurtzustandsanzeige_Beifahrer_GWF_GZA_BF → nicht_aktiv // Значок ремня пассажира
- SBR_PreWarning_Fahrer → nicht_aktiv                    // Звук при отстёгивании (водитель)
- SBR_PreWarning_Beifahrer → nicht_aktiv                 // Звук при отстёгивании (пассажир)

Блок: ACSM → 3001
Параметры:
- GWF_SBR_WARNDAUER → werte=01 // Длительность предупреждения (default: 5A = 90 сек)
```

### Настройка параметров для G-серии

```text
Блок: FA → HO-WORT
Параметры:
- Добавить OI11 → Calculate FP → Code ACSM // Отключение гонга ремня через FA

Блок: DKOMBI4 → 3000
Параметры:
- FOND_GURTSTATUS_ENABLE → inaktiv // Убрать значок ремней задних пассажиров
```

---

## Удаление дисклеймеров в iDrive

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3001
Параметры:
- LEGAL_DISCLAIMER_TIME → kein_ld        // Убрать дисклеймер при запуске iDrive
- MACRO_CAM_LEGALDISCLAIMER → kein_ld    // Убрать дисклеймер камеры/PDC
```

---

## Активная мёртвая зона (скорость активации)

### Настройка параметров для F-серии

```text
Блок: ICM → 3000
Параметры:
- C_ZSW_Aktivierunggeschwindigkeit_Funktion_low → 20_kmh // Порог активации (default: 50_kmh)
```

> [!NOTE]
> Не устанавливать ниже 20 км/ч. Значение по умолчанию — 50 км/ч.

---

## Отключение клаксона при закрытии (G-series)

### Настройка параметров для G-серии

```text
Блок: BDC_BODY → 7083
Параметры:
- AM_HORN_AT_SECURE → nicht_aktiv // Убрать клаксон при закрытии с заведённым двигателем
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка         | Как проверить настройку / Решение                           |
| :------------------------ | :---------------------------------------------------------- |
| Гонг ремня не отключается | Проверить все 9 параметров ACSM + GWF_SBR_WARNDAUER         |
| Дисклеймер остаётся       | Проверить LEGAL_DISCLAIMER_TIME + MACRO_CAM_LEGALDISCLAIMER |
| Мёртвая зона не работает  | Проверить наличие опции, C_ZSW_Aktivierunggeschwindigkeit   |

---

> [!WARNING]
> Отключение напоминаний о ремне безопасности снижает уровень
> безопасности. В ряде стран это может быть незаконно. Используйте
> на свой страх и риск.
