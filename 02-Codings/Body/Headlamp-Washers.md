# Headlamp Washers (Омыватель фар)

> [!IMPORTANT]
> **FEM_BODY** — требуется наличие омывателя фар (Cold Weather Package).

---

## Полное отключение омывателя фар

### Настройка параметров для F-серии

```text
Блок: FEM_BODY → 3080
Параметры:
- WW_SCHEINWERFERREINIGUNG → nicht_aktiv // Полное отключение (default: aktiv)
```

---

## Тонкая настройка омывателя

### Настройка параметров для F-серии

```text
Блок: FEM_BODY → 3080
Параметры:
- WW_ANZAHL_SPRITZIMPULSE_SRA → 3_Impulse          // Кол-во импульсов (default: 2_Impulse)
- WW_ANZAHL_WASCHBET_ZUR_SRA → user                // Кол-во омываний до активации (default: 10)
- WW_DAUER_SPRITZIMPULSE_SRA → werte=0A            // Длительность импульса (HEX × 100 мс, default: 0A = 1000 мс)
- WW_SRA_GESCHWINDIGKEITS_DEAKTIVIERUNG → werte=82 // Макс. скорость активации (HEX, default: 82 = 130 км/ч)
- WW_PAUSE_SPRITZIMPULSE_SRA → werte=0A            // Пауза между импульсами (HEX × 100 мс)
- WW_SRA_SPERRZEIT → werte=0A                      // Время до повторной активации (HEX × 1 мин)

Блок: FEM_BODY → 3081
Параметры:
- WW_ANZAHL_NACHWISCHZ_FRONT → 3_mal_Nachwischen   // Кол-во проходов дворников после омывания
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка        | Как проверить настройку / Решение                                 |
| :----------------------- | :---------------------------------------------------------------- |
| Омыватель не работает    | Проверить WW_SCHEINWERFERREINIGUNG, наличие опции                 |
| Слишком частая активация | Увеличить WW_ANZAHL_WASCHBET_ZUR_SRA                              |
| Большой расход жидкости  | Уменьшить WW_ANZAHL_SPRITZIMPULSE_SRA, WW_DAUER_SPRITZIMPULSE_SRA |

---

> [!WARNING]
> Отключение омывателя фар снижает безопасность в зимний период.
> Фары могут загрязняться и терять эффективность.
