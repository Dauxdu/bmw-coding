[English](Sport-Features.md) | **Русский**

# Sport Features

> [!IMPORTANT]
> **HU_NBT, KOMBI, ASD, ICM, EGS** — сводный файл спортивных функций.

---

## Спортивные индикаторы в стиле M

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3000
Параметры:
- M_VEHICLE → aktiv // Цвет шкал в Sport Display: красный/серебристый (default: nicht_aktiv)
```

> [!NOTE]
> Меняет цвет шкал в спортивных дисплеях с янтарного (BMW) на
> красный/серебристый (M-стиль).

---

## Звук уведомлений (гонг)

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3002
Параметры:
- SOUND_SIGNAL_SET → 03_BMW_i // Звук уведомлений (default: 00_BMW)
```

### Таблица значений SOUND_SIGNAL_SET

| Звук          | Значение    |
| :------------ | :---------- |
| BMW (default) | 00_BMW      |
| BMW i         | 03_BMW_i    |
| Mini          | mini        |
| Rolls-Royce   | rolls_royce |

---

## Active Sound Design (ASD)

### Настройка параметров для F-серии

```text
Блок: ASD → 3000
Параметры:
- Model Range → F010  // Модельный ряд (default: F030)
- Engine → S63B44     // Звук двигателя (default: N26B20)
```

### Таблица значений ASD

| Модель    | Model Range | Engine | Звук          |
| :-------- | :---------- | :----- | :------------ |
| M5/M6     | F010        | S63B44 | V8 Twin-Turbo |
| M3/M4     | F080        | S55B30 | I6 Twin-Turbo |
| 328i/428i | F030        | N26B20 | I4 Turbo      |
| ASD Off   | F020        | S63B44 | Выключено     |

> [!NOTE]
> ASD доступен только на F3x 2014+ с двигателями N20 и некоторыми N55.
> Если блок ASD виден в E-Sys — его можно модифицировать.

---

## Меню ASD в iDrive

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3000
Параметры:
- ASD_CONFIGURATION → aktiv // Меню настройки ASD в iDrive — Part 1
- ASD_SOUND_4 → aktiv       // Меню настройки ASD в iDrive — Part 2
```

---

## Стартовая анимация iDrive

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3001
Параметры:
- STARTUP_EMBLEM → variant_1 // Стартовая анимация (default: variant_0)
- STARTUP_TYPE → black       // Тип заставки (default: animation)
```

### Таблица значений STARTUP_EMBLEM

| Анимация            | Значение                        |
| :------------------ | :------------------------------ |
| BMW Connected Drive | variant_0, variant_2, variant_6 |
| ///M                | variant_1                       |
| BMW i               | variant_3                       |
| Mini                | variant_4                       |
| Rolls-Royce         | variant_5                       |
| BMW White           | variant_7                       |
| BMW Brown           | variant_8                       |
| Merry Christmas     | variant_9                       |

### Настройка параметров для G-серии

```text
Блок: HU_MGU → 3000
Параметры:
- STARTUP_EMBLEM → bmw / M / alpina / rr // Стартовая анимация (G)
- HMI_BRAND → BMW_M                      // M-style тема оформления (G, i-Step ≥ 2019)
- BRAND → bmw / mini / rr / bmw_i        // Звуковые предупреждения (G)
```

---

## Полоска громкости на экране

### Настройка параметров для F-серии

```text
Блок: HU_NBT → 3000
Параметры:
- VOLUME_POPUP_DISPLAY → aktiv // Полоска громкости при регулировке (default: nicht_aktiv)
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка              | Как проверить настройку / Решение                       |
| :----------------------------- | :------------------------------------------------------ |
| ASD не работает                | Проверить наличие блока ASD, версию прошивки, двигатель |
| Стартовая анимация не меняется | Проверить STARTUP_EMBLEM + STARTUP_TYPE                 |
| Звук не меняется               | Проверить SOUND_SIGNAL_SET, перезагрузить ГУ            |

---

> [!WARNING]
> ASD влияет на восприятие звука двигателя. Неверные значения Model
> Range / Engine могут привести к некорректному звуку или ошибке
> блока ASD.
