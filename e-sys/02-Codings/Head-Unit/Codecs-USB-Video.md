**English** | [Русский](Codecs-USB-Video.ru.md)

# Codecs & USB Video

> [!IMPORTANT]
> **HU_NBT** — the main head unit with USB video support.

---

## Enabling Codec Support

### Parameter settings for F-series

```text
ECU: HU_NBT → 3000
Parameters:
- ENT_CODEC_OGG → aktiv        // OGG codec
- ENT_CODEC_XVID → aktiv       // XVID codec
- ENT_CODEC_XVCD → aktiv       // XVCD codec
- ENT_CODEC_VCD → aktiv        // VCD codec
- ENT_MC_VIDEO_SUPPORT → aktiv // MC Video support
- ENT_VIDEO_HMI → aktiv        // "DVD Menu" button when watching a DVD

ECU: HU_NBT → 3003
Parameters:
- API_USB_VIDEO → both // USB Video (front + rear, default: none)
```

> [!NOTE]
> Supported formats: AVI, MP4, MKV (with Xvid, DivX codecs),
> OGG video, video with subtitles (limited).

---

## File Requirements

```text
Recommended parameters:
- Resolution: up to 1920×1080 (Full HD)
- Bitrate: up to 10–15 Mbit/s
- File system: FAT32 or exFAT
- File name: Latin characters, no special characters

Not supported:
- HEVC / H.265
- 4K video
- Files > 32 GB (FAT32 limit)
```

---

## Notes and Troubleshooting

| Problem / Error        | How to check / Solution                              |
| :--------------------- | :--------------------------------------------------- |
| Video does not play    | Check the codec, resolution and file name            |
| Sound but no picture   | Check the video codec (XVID/OGG), re-encode the file |
| USB drive not detected | Format as FAT32, check the USB port                  |

---

> [!WARNING]
> For guaranteed compatibility, convert video to:
> MP4/AVI container, Xvid/H.264 video, MP3/AAC audio,
> 1280×720 or 1920×1080 resolution.
