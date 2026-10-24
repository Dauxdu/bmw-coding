**English** | [Русский](CarPlay.ru.md)

# CarPlay

> [!IMPORTANT]
> **HU_NBT, HU_NBT_EVO, HU_MGU** — depending on the head unit generation.
> Hardware support is required (a WiFi module for wireless).

---

## Basic CarPlay Activation

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- CARPLAY → aktiv // Activate Apple CarPlay
```

### Parameter settings for G-series

```text
ECU: HU_MGU → 3000
Parameters:
- CARPLAY → aktiv      // Activate Apple CarPlay
- WIFI_HOTSPOT → aktiv // Wireless CarPlay (requires a WiFi module)
```

> [!NOTE]
> Wired CarPlay: only requires activating the parameter.
> Wireless: requires a WiFi module and activating WIFI_HOTSPOT.
> iPhone with iOS 13+.

---

## Notes and Troubleshooting

| Problem / Error          | How to check / Solution                                   |
| :----------------------- | :-------------------------------------------------------- |
| CarPlay does not connect | Check the cable, the CARPLAY parameter, the iOS version   |
| Wireless does not work   | Make sure a WiFi module is present, activate WIFI_HOTSPOT |
| No sound / dropouts      | Restart the head unit and the phone, check the cable      |

---

> [!WARNING]
> After a head unit firmware update, the activation parameters may be
> reset. Keep a backup of your codings.
