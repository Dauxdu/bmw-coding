# Traffic Sign Recognition

> [!IMPORTANT]
> **KAFAS(2)** — камера распознавания, **KOMBI** / **HUD** — отображение знаков

---

## Русификация / настройка региона

```
Блок: KAFAS2
Параметры:
- COUNTRY_VARIATION → ECE
- COD_CAM_ONLY → camera_only
- COUNTRY_CODING_DISPLAY → ECE_white
- TSM_COUNTRY_VARIATION → ece
```

> [!TIP]
>
> - `ECE` — европейский стандарт дорожных знаков
> - `camera_only` — использование только данных камеры (без навигации)
> - `ECE_white` — белый фон для отображения в меню

---

## Отображение знаков

### На приборной панели

```
Блок: KOMBI
Параметры:
- TRAFFIC_SIGN_DISPLAY → aktiv
- SIGN_PRIORITY_LIST → настроить порядок
```

### В проекционном дисплее (если есть)

```
Блок: HUD
Параметр: HUD_TRAFFIC_SIGNS → aktiv
```

---

## Типы распознаваемых знаков

```
Блок: KAFAS2
Параметры:
- SIGN_SPEED_LIMIT → aktiv
- SIGN_NO_OVERTAKING → aktiv
- SIGN_NO_ENTRY → aktiv
- SIGN_CUSTOMS → aktiv (по желанию)
- SIGN_TEMPORARY → aktiv (временные знаки)
```

---

## Настройка чувствительности

```
Блок: KAFAS2
Параметры:
- SIGN_RECOGNITION_CONFIDENCE → high || medium || low
- SIGN_UPDATE_FREQUENCY → настроить частоту обновления
- SIGN_DISPLAY_DURATION → настроить время отображения
```

---

## Предупреждения о превышении скорости

```
Блок: [соответствующий]
Параметры:
- SPEED_WARNING_THRESHOLD → +5 км/ч / +10 км/ч / выкл
- SPEED_WARNING_TYPE → visual || acoustic
```

---

## Troubleshooting

| Проблема              | Решение                                              |
| --------------------- | ---------------------------------------------------- |
| Знаки не распознаются | Проверить регион (COUNTRY_VARIATION), чистоту камеры |
| Неправильные знаки    | Убедиться, что выбран правильный регион (ECE для РФ) |
| Знаки не отображаются | Проверить параметры в KOMBI / HUD                    |
| Ошибка в KAFAS        | Выполнить калибровку камеры                          |

---

> [!NOTE]
>
> - Работает только при хорошей видимости
> - Может не распознавать временные/нестандартные знаки
> - Требует чистого лобового стекла в зоне камеры
