# Adaptive Lighting (Cornering Lights)

> [!IMPORTANT]
> **FEM_BODY, FRM** — F-series → FEM_BODY; альтернатива через FRM.
> Требуется наличие передних ПТФ. Режим фар: AUTO, тёмное время суток.

---

## Адаптивное освещение поворотов через ПТФ

### Настройка параметров для F-серии

```text
Блок: FEM_BODY → 3073
Параметры:
- C_CLC_ENA → F030enable   // Включение cornering lights — Part 1 (default: F030disable)
- C_BLC_ENA → aktiv        // Включение cornering lights — Part 2 (default: nicht_aktiv)
- KL_ENABLE_RE → KL_Ein    // Включение cornering lights — Part 4 (default: KL_Aus)

Блок: FEM_BODY → 3066
Параметры:
- KL_ENABLE_LI → KL_Ein    // Включение cornering lights — Part 3 (default: KL_Aus)

Блок: FEM_BODY → 3062
Параметры:
- MAPPING_abbiegel_L_output → nsw_l // Маппинг левой ПТФ на поворотный свет (default: Off)
- MAPPING_abbiegel_R_output → nsw_r // Маппинг правой ПТФ на поворотный свет (default: Off)
```

> [!NOTE]
> При повороте руля в тёмное время суток (режим AUTO) включается
> соответствующая ПТФ для подсветки зоны поворота. Все 6 параметров
> обязательны. Порядок: Part 1 → Part 2 → Part 3 → Part 4 → Part 5 → Part 6.

---

## Альтернативная настройка через FRM

### Настройка параметров для F-серии (F01, F10, F25)

```text
Блок: FRM
Параметры:
- Lamp_map_para_satz_01 → BV_F025_WERT02_Corneringlight-UBER-NSW
- Lamp_map_para_satz_02 → BV_F025_WERT02_Corneringlight-UBER-NSW
- ALC_AFS_ENABLE → aktiv
- U_EFF_CL → FF            // Для LED-фар (или wert_07__13,0V = 82 для галогена)
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка             | Как проверить настройку / Решение                          |
| :---------------------------- | :--------------------------------------------------------- |
| Адаптивный свет не включается | Проверить режим фар (AUTO), время суток, датчик света      |
| Работает только одна сторона  | Проверить MAPPING_abbiegel_L/R_output, проводку, лампу ПТФ |
| Ошибка в блоке                | Выполнить калибровку фар через сервисные функции           |

---

> [!WARNING]
> После изменений в настройках освещения рекомендуется выполнить
> адаптацию фар через диагностический сканер или сервисное меню E-Sys.
