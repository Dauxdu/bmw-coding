[English](Instrument-Cluster.md) | **Русский**

# Instrument Cluster (KOMBI)

> [!IMPORTANT]
> **KOMBI, DKOMBI4, ICM** — F-series → KOMBI; G-series → DKOMBI4.

---

## Цифровой спидометр

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- BC_DIGITAL_V → aktiv // Текущая скорость цифрами в списке BC на экране KOMBI
```

### Настройка параметров для G-серии

```text
Блок: DKOMBI4 → 3000
Параметры:
- DIGIT_GESCHW_ENABLE → anzeige_kmh // Цифровая скорость на приборной панели
- DIGIT_GESCHW_UPDATERATE → 2       // Частота обновления скорости
```

---

## Логотип M Performance при запуске

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- BMW_LOGO → mpm // Логотип M Performance (default: ag = Alpina)
```

### Таблица значений BMW_LOGO

| Логотип          | Значение |
| :--------------- | :------- |
| Alpina (default) | ag       |
| M Performance    | mpm      |
| BMW стандартный  | bmw      |

### Настройка параметров для G-серии

```text
Блок: DKOMBI4 → 3000
Параметры:
- GLOBAL_LAYOUT_VARIANTE → M / ALPINA / M_Performance // Layout приборной панели
- LOGO_SCHRIFTZUG → msp_logo                          // Логотип M в Sport-режиме
- MPA_MSP_VIEW_ENABLE → grau_weiss                    // Серый цвет в Sport-режиме
```

---

## Отключение коррекции спидометра

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- BC_V_KORREKTUR → nicht_aktiv // Отображение реальной скорости без коррекции (default: aktiv)
```

> [!NOTE]
> При отключении коррекции скорость на спидометре будет ~2 км/ч ниже
> установленной скорости круиз-контроля.

---

## Авто-сброс бортового компьютера

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- BC_AUTORESET_ZEIT → werte=04 // Авто-сброс БК (HEX часов, default: 04 = 4 часа, FF = никогда)
```

---

## Белая подсветка KOMBI ночью

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3007
Параметры:
- DIM_NACHT_EIN → werte=FF // Белая подсветка ночью (default: 32 = оранжевая)
```

---

## Иконка Sport+ на KOMBI

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- FDS_MENUE_TEXT_1 → menue_3   // Иконка Sport+ (default: menue_4)
- FDS_MENUE_TEXT_2 → menue_3
- FDS_MENUE_TEXT_3 → menue_3
- FDS_MENUE_TEXT_4 → menue_3
- FDS_MENUE_SIGNAL_1 → menue_3 // Сигнал Sport+ (default: menue_4)
- FDS_MENUE_SIGNAL_2 → menue_3
- FDS_MENUE_SIGNAL_3 → menue_3
- FDS_MENUE_SIGNAL_4 → menue_3
```

---

## Функция LIM (ограничитель скорости)

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3003
Параметры:
- SLD_ENABLE → aktiv // LIM функция — Part 1

Блок: ICM → 3000
Параметры:
- SLD_Funktion → aktiv                    // LIM функция — Part 2
- C_Umschaltung_ACC_DCC → zugelassen      // LIM функция — Part 3 (default: unterdruecken)
- LDM_SET_Taste → nur_SET__O              // LIM функция — Part 4 (default: SET_und_aktivieren__IO)
```

> [!NOTE]
> Кнопка «Set» круиз-контроля начинает работать как кнопка «LIM»
> (ограничитель скорости). Все 4 параметра обязательны.

---

## Отключение уведомления MSA на KOMBI

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- MSA_VERFUEGBARANZEIGE_ENABLE → nicht_aktiv // Убрать «Auto Start-Stop Off» (default: aktiv)
```

---

## Отключение гонга задней передачи

### Настройка параметров для F-серии

```text
Блок: KOMBI → 3000
Параметры:
- R_GANG_AKUSTIK_ENABLE → nicht_aktiv // Убрать звуковой сигнал при включении R (default: aktiv)
```

---

## Замечания и важные моменты (Troubleshooting)

| Проблема / Ошибка                  | Как проверить настройку / Решение                               |
| :--------------------------------- | :-------------------------------------------------------------- |
| Цифровой спидометр не отображается | Проверить BC_DIGITAL_V, версию прошивки KOMBI                   |
| Логотип не меняется                | Убедиться, что значение mpm/ag поддерживается версией KOMBI     |
| LIM не работает                    | Проверить все 4 параметра (KOMBI + ICM), наличие круиз-контроля |

---

> [!WARNING]
> При кодировании KOMBI не отключайте питание. Используйте стабильное
> напряжение (подключите ЗУ). Сохраните резервную копию оригинальной
> кодировки перед записью.
