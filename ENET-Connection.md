**English** | [Русский](ENET-Connection.ru.md)

# ENET Connection

> [!IMPORTANT]
> **ENET cable (OBD-II → RJ45)** — the physical connection to the vehicle bus.
> A stable battery supply of ≥ 12.5 V is required.

---

## Connection Procedure

1. Switch on the ignition or start the engine
2. Wait 30 seconds (MOST/FlexRay bus initialization)
3. Plug the OBD connector into the vehicle
4. Wait 30 seconds (interface detection)
5. Connect the ENET cable to the laptop (RJ45)

---

## Notes and Troubleshooting

| Problem / Error         | How to check / Solution                                |
| :---------------------- | :----------------------------------------------------- |
| Does not connect        | Check the cable and ignition, restart E-Sys            |
| "No response from ECUs" | Wait 60 s, check that the battery is > 12.5 V          |
| Frequent disconnects    | Disable USB power saving, use a good-quality cable     |
| Functions are blocked   | Check the ignition status and the battery charge level |

---

> [!WARNING]
> Do not disconnect the ENET cable during read/write operations — this may
> cause an irreversible ECU error. Always connect a battery charger during
> long sessions.
