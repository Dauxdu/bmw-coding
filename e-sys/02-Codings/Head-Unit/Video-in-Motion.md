**English** | [Русский](Video-in-Motion.ru.md)

# Video in Motion

> [!IMPORTANT]
> **HU_NBT, HU_CIC** — HU_ENTRY does not support Video in Motion.
> G-series → HU_NBT_EVO / HU_MGU.

---

## Basic Video-in-Motion Unlock

### Parameter settings for F-series (HU_NBT)

```text
ECU: HU_NBT → 3000
Parameters:
- SPEEDLOCK_X_KMH_MIN → werte=FF               // Remove the video lock (min. speed)
- SPEEDLOCK_X_KMH_MAX → werte=FF               // Remove the video lock (max. speed)
- VIDEO_HANDBRAKE → nicht_aktiv                // Remove the handbrake requirement
- VIDEO_FRONT_LOCKED → nicht_aktiv             // Remove Front Lock
- VIDEO_SPEEDLOCK_CONDITION → none             // Remove the speed condition
- SPEEDLOCK_FREISCHALTMENU → aktiv             // Unlock menu in Media
- SERVICES_MESSAGES_SPEEDLOCK_CONDITION → none // Service messages while driving
- OFFICE_MESSAGES_SPEEDLOCK_CONDITION → none   // Office messages while driving
```

### Parameter settings for F-series (HU_CIC)

```text
ECU: HU_CIC → 3000
Parameters:
- SPEEDLOCK_X_KMH_MIN → werte=FF         // Remove the video lock (min)
- SPEEDLOCK_X_KMH_MAX → werte=FF         // Remove the video lock (max)
- VIDEO_NUR_MIT_HANDBREMSE → nicht_aktiv // Remove the handbrake requirement
```

### Parameter settings for G-series

```text
ECU: HU_NBT_EVO → 3000
Parameters:
- SPEEDLOCK_SPEEDVALUE_MIN → werte=1F   // Remove the lock (G)
- SPEEDLOCK_SPEEDVALUE_MAX → werte=3F   // Remove the lock (G)
- SPEEDLOCK_FREISCHALTMENU → aktiv      // Unlock menu (G)
```

---

## Alternative Method via the Menu (NBT)

```text
1. Push the iDrive controller up (hold)
2. Go to: Media → Menu → Media → CD/MM
3. Deactivate Speedlock → Yes
```

> [!NOTE]
> Requires `SPEEDLOCK_FREISCHALTMENU → aktiv` to be set first.

---

## Owner's Manual in Motion

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- SL06_IBA_1 → nicht_aktiv // Manual while driving — Part 1 (default: aktiv)
- SL07_IBA_2 → nicht_aktiv // Manual while driving — Part 2 (default: aktiv)
- SL21_IBA_3 → nicht_aktiv // Manual while driving — Part 3 (default: aktiv)
```

---

## Cameras While Driving

### Parameter settings for F-series

```text
ECU: REM/PMA
Parameters:
- V_SCHWELLE_1 → werte=FF // Top view camera cut-off speed (FF = 255 km/h, default: 24)
- V_SCHWELLE_2 → werte=FF // Rear camera cut-off speed (FF = 255 km/h, default: 0F)
- D_SCHWELLE_1 → werte=FF // Top view camera cut-off distance (FF = 255 m, default: 32)
- D_SCHWELLE_2 → werte=FF // Rear camera cut-off distance (FF = 255 m, default: 0A)

ECU: TRSVC → 3000
Parameters:
- SV_Activate_Speed_Limit → werte=FF   // Side camera at any speed — Part 1
- SV_Deactivate_Speed_Limit → werte=FF // Side camera at any speed — Part 2
```

---

## Camera When Rolling Backwards

### Parameter settings for F-series

```text
ECU: PMA
Parameters:
- AKT_RUECKWAERTSROLLEN → aktiv // Camera turns on when rolling backwards without engaging R
```

> [!NOTE]
> The PMA module is only present with the parking assistant.

---

## Notes and Troubleshooting

| Problem / Error              | How to check / Solution                               |
| :--------------------------- | :---------------------------------------------------- |
| Video is still locked        | Check all SPEEDLOCK parameters, restart the head unit |
| Black screen during playback | Check the video format, codec and resolution          |
| Camera turns off at speed    | Check V_SCHWELLE_1/2, D_SCHWELLE_1/2 in REM/PMA       |

---

> [!WARNING]
> Watching video while driving is prohibited for the driver by traffic law
> in most countries. Use this function for passengers only.
