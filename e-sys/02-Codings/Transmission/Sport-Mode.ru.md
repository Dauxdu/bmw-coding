[English](Sport-Mode.md) | **Русский**

# Sport Mode & Driving Modes

> [!IMPORTANT]
> **ICM, EGS, DME/DDE, HU_NBT, BDC_BODY, HU_MGU** — F-series → ICM + EGS;
> G-series → BDC_BODY + HU_MGU.

---

## Спортивная логика АКПП (Sport Auto Transmission)

### VO Coding для F-серии

```text
1. Открыть FA автомобиля в E-Sys
2. Изменить опцию 205 → 2TB
3. Нажать «Calculate FP»
4. Закодировать блоки: EGS, ICM, KOMBI
```

### Настройка параметров для F-серии

```text
Блок: ICM → 3000
Параметры:
- IcmKod_B_S2TBA → verbaut               // Спортивная логика АКПП (default: nicht_verbaut)
- ICMKOD_B_SPORTLENKUNG → aktiv          // Режим Sport+ (default: nicht_aktiv)
- ICMKOD_B_InitEco → verbaut             // Eco Pro по умолчанию при запуске (default: nicht_verbaut)
- ICMKOD_B_SPORTINDIVIDUALISIERBAR → ein // Настройка Sport в iDrive — Part 2 (default: aus)
- C_Abstandsstufe_init → Stufe_1         // Минимальная дистанция ACC при запуске (default: Stufe_4)

Блок: EGS → 3000
Параметры:
- Sportschalter → aktiv      // Спортивная логика переключений
- Sportschalter_alt → aktiv  // Спортивная логика (альтернативный)
- Applikation_LC → aktiv     // Launch Control (требует 2TB в FA)
```

### Настройка параметров для G-серии

```text
Блок: BDC_BODY → 3221
Параметры:
- FesSportWorldMode1 → SportExpert     // Режим Sport+ (G)
- FesComfortWorldMode1 → ComfortPlus   // Режим Comfort+ (G)
- FesEcoWorldMode1 → ecoproplus        // Режим Eco Pro+ (G)
- FesPiaDefaultLastUserMode → 04       // Режим по умолчанию (01=Sport, 04=Comfort, 07=EcoPro)

Блок: HU_MGU → 3000
Параметры:
- FES_SPORT_EXPERT → aktiv   // Пункт Sport+ в меню (G)
- FES_COMFORT_PLUS → aktiv   // Пункт Comfort+ в меню (G)
- FES_ECO_PLUS → aktiv       // Пункт Eco Pro+ в меню (G)
```

> [!NOTE]
> Sport Auto Transmission обеспечивает более поздние переключения на
> повышенную, более ранние сбросы на пониженную и агрессивную реакцию
> на педаль газа. Также активирует режим Sport+.

---

## Настройка Sport в iDrive

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3000
Параметры:
- Macro_fds → popup_and_config // Настройка Sport-режима в iDrive (default: popup_only)
```

---

## Отключение рекуперации (IGR)

### Настройка параметров для F-серии

```text
Блок: DME → 3000
Параметры:
- IGR → werte=00 // Рекуперация отключена, АКБ заряжается до 100% (default: ~80%)
```

> [!NOTE]
> По умолчанию АКБ заряжается до ~80%, оставляя 20% для рекуперации.
> Отключение = заряд до 100%, но +~3% к расходу топлива.

---

## Режим наката в Eco Pro (Segeln / Sailing)

### Настройка параметров для F-серии

```text
Блок: FEM_BODY
Параметры:
- SEGELN_ENABLE → aktiv // Режим наката — Part 1

Блок: HU_NBT
Параметры:
- EFF_DYN_SAILING → aktiv // Режим наката — Part 2 (пункт в настройках Eco Pro)

Блок: ICM
Параметры:
- C_Segeln_vorhanden → enable // Режим наката — Part 3

Блок: EGS
Параметры:
- Segeln → aktiv // Режим наката — Part 4
```

> [!NOTE]
> Только для АКПП. Кодировать все 4 блока. В Eco Pro при отпускании
> газа на скорости ~50–160 км/ч коробка размыкается и машина катится
> накатом.

---

## Спортивные дисплеи (HU_CIC)

### Настройка параметров для F-серии (без навигации)

```text
Блок: HU_CIC → 3000
Параметры:
- EFF_DYN_SPORT_CID → aktiv  // Спортивные дисплеи на iDrive без навигации
- EFF_DYN_SPORT_UNIT → aktiv // Единицы измерения в спортивных дисплеях
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка          | Как проверить настройку / Решение                             |
| :------------------------- | :------------------------------------------------------------ |
| Режимы не переключаются    | Проверить кнопку, ICMKOD_B_SPORTLENKUNG, версию прошивки      |
| АКПП не меняет логику      | Убедиться, что закодирован ICM + EGS, выполнить адаптацию КПП |
| Launch Control не работает | Проверить Applikation_LC, наличие 2TB в FA                    |

---

> [!WARNING]
> После изменений в настройках трансмиссии рекомендуется выполнить
> адаптацию КПП через сервисные функции E-Sys. VO Coding (2TB)
> сбрасывает FDL-значения в EGS, ICM, KOMBI до заводских.
