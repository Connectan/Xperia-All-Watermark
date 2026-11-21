# Xperia All Watermark

[日本語](README.md) | **English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/status-Beta%202%20(BugFix)-orange)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**An Android app that adds a "Taken with Xperia" logo and shooting info as a watermark to photos taken on an Xperia. It works with every Xperia, not just the ZEISS models.**

The app reads the photo's EXIF data: model name, 35mm-equivalent focal length, aperture, shutter speed, ISO, and date/time. It places this as a watermark at the bottom center of the photo and saves the result as a new image.

> Looking for the ZEISS-only version with an "Xperia × ZEISS" logo? → [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss)

---

## ⚠️ Read this first

- The APK here is the **bug-fix build of Beta 2**. It is still a debug build.
- The package name is `com.aistudio.xperiawatermark.xpwm`. It is a separate app from the ZEISS version, so **you can install both at the same time**.
- This app is not distributed through Google Play. Use it at your own risk.

---

## Download

👉 **[Download the APK from Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest)**

| Item | Details |
|---|---|
| File name | `XperiaAllWatermark_Beta2_BugFix_Lastest.apk` |
| Size | About 22 MB |
| SHA-256 | `511b238ee9accce01bfa0c6b1e27d0bff3076be44d516956da662a3a2c6e8a6e` |

---

## Features

| Feature | Details |
|---|---|
| Finds Xperia photos automatically | Scans the photos on your device. It uses the EXIF model name (model codes like `SO-`, `SOG`, `XQ-`) to find **JPEG photos taken on an Xperia** and lists them |
| Adds the watermark | Places a large "Taken with Xperia" logo and the shooting info at the bottom center of the photo. The result is saved as a separate file, so the original photo stays untouched |
| Choose what to include | In the watermark settings, choose whether to include the logo, the camera model, the shooting parameters (focal length, aperture, shutter speed, ISO), and the date/time |
| Preview before saving | Check the result first, then tap "Save watermark to this photo" to save just that one |
| Batch processing | Multi-select, "Select all", or "Select unprocessed only", then apply them all at once. Progress and the number of successes and errors are shown while it works |
| No duplicate saves | Photos that already have a watermarked copy are safely skipped during batch processing |
| Filters | Switch the list between "All", "Unprocessed", and "Processed". Processed photos get a "Watermarked" mark |
| Rescan | Reload right away to pick up photos you just took |

### What goes into the watermark

| Item | Example |
|---|---|
| Logo | Taken with Xperia |
| Camera model | Xperia 1 VI |
| Focal length (35mm equivalent) | 24mm |
| Aperture | F1.9 |
| Shutter speed | 1/125s |
| ISO | ISO 100 |
| Date/time | When the photo was taken |

\* These example values are for illustration. The actual values come straight from the photo's EXIF.

---

## Supported models

- **Any photo whose EXIF model name is an Xperia model code is supported** (`SO-`: docomo, `SOG`: au, `XQ-`: SIM-free and international models, and so on).
- A ZEISS lens is not required. Photos from the Xperia 1, 5, and 10 series, or any other Xperia, are all supported.
- Detection is based on **which phone took the photo**, not which phone the app is installed on. So you can add watermarks to Xperia photos on other Android phones too.
- **It does not work with photos taken on non-Xperia phones, or with photos whose EXIF data has been removed.**

### Differences from the ZEISS version

| | Xperia All Watermark (this app) | [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss) |
|---|---|---|
| Supported photos | Photos taken on **any Xperia** | Only photos taken on ZEISS-equipped Xperia phones |
| Logo | Taken with Xperia | Xperia × ZEISS |
| Package name | `com.aistudio.xperiawatermark.xpwm` | `com.example` |

---

## How to use

1. Open the app and tap "Allow storage permission" to **allow** access to your photos
2. After "Scanning storage for Xperia photos…", the photos taken on an Xperia appear in a list
3. **For a single photo:** tap the photo → check it in the watermark preview → "Save watermark to this photo"
4. **For several photos:** select them ("Select all" and "Select unprocessed only" are also available)
5. In **Watermark settings**, choose the items you want to include
6. Tap "Apply watermark to the ○ selected photos" to save them all at once
7. When "Batch processing complete!" appears, tap "Done"

\* The app's screens are in Japanese. The button names above are translated.

Images are saved to **`Pictures/Xperia_Watermarked`**.

---

## How to install

1. Download the APK from [Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest)
2. Tap the downloaded APK
3. If you are asked about "unknown apps", turn on **Allow from this source** for your browser (or file manager)
4. Tap "Install"

> Because this is installed from outside Google Play, Play Protect may show a warning. If it does, tap "More details" → "Install anyway".

---

## Requirements

| Item | Details |
|---|---|
| Android | **7.0 or later** (API 24+) |
| Target | Android 16 (API 36) |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| Photos | JPEGs taken on an Xperia (with EXIF) |

---

## Permissions

| Permission | What it's for |
|---|---|
| Photos and videos (`READ_MEDIA_IMAGES`) | To find photos on the device and add watermarks (Android 13+) |
| Selected photos (`READ_MEDIA_VISUAL_USER_SELECTED`) | For when you choose "Allow only selected photos" (Android 14+) |
| Read storage (`READ_EXTERNAL_STORAGE`) | To find photos (Android 12 and earlier) |
| Write storage (`WRITE_EXTERNAL_STORAGE`) | To save watermarked images (Android 9 and earlier) |
| Internet (`INTERNET`, `ACCESS_NETWORK_STATE`) | Declared by libraries bundled in the app, such as Firebase |
| `DUMP` | Declared by a library. Regular apps are never granted this permission |

---

## FAQ

**Q. My photos don't show up in the list**
A. Photos taken on non-Xperia phones, or photos whose EXIF (shooting info) has been removed, will not appear. Images saved from social media or exported from editing apps often have no EXIF. For photos you just took, tap "Rescan".

**Q. Will my original photos be overwritten?**
A. No. The watermarked image is saved **as a separate file** in `Pictures/Xperia_Watermarked`.

**Q. Will batch processing save the same photo more than once?**
A. No. Photos that already have a watermarked copy are skipped automatically during batch processing.

**Q. Can I install it alongside the ZEISS version?**
A. Yes. The package names are different, so they install as separate apps.

---

## Author

**Connectan (こねくたん)**, also known as 晓玲 清風
- Website: https://connectan.github.io

Lives deep in the rabbit hole of Chinese phones without Japanese certification.

---

## Notes

- "Xperia" is a trademark of Sony Group Corporation.
- This is an **unofficial app made by an individual**. It is not affiliated with Sony.
- Use at your own risk.
