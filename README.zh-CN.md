# Xperia All Watermark

[日本語](README.md) | [English](README.en.md) | **简体中文** | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/status-Beta%202%20(BugFix)-orange)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**一款给 Xperia 拍摄的照片加上“Taken with Xperia”标志和拍摄信息水印的 Android 应用。不只是蔡司（ZEISS）机型，所有 Xperia 都支持。**

应用会从照片的 EXIF 中读取机型、35mm 等效焦距、光圈、快门速度、ISO 和拍摄时间，把它们作为水印合成在照片底部中央，并另存为新图片。

> 只支持蔡司 Xperia、加“Xperia × ZEISS”标志的版本在这里 → [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss)

---

## ⚠️ 请先阅读

- 这里发布的 APK 是 **Beta 2 的 Bug 修复版**，仍然是调试（debug）版本。
- 包名为 `com.aistudio.xperiawatermark.xpwm`。它和蔡司版是不同的应用，**可以同时安装**。
- 本应用不通过 Google Play 发布，使用风险请自行承担。

---

## 下载

👉 **[从 Releases 下载 APK](https://github.com/Connectan/Xperia-All-Watermark/releases/latest)**

| 项目 | 内容 |
|---|---|
| 文件名 | `XperiaAllWatermark_Beta2_BugFix_Lastest.apk` |
| 大小 | 约 22 MB |
| SHA-256 | `511b238ee9accce01bfa0c6b1e27d0bff3076be44d516956da662a3a2c6e8a6e` |

---

## 功能

| 功能 | 说明 |
|---|---|
| 自动查找 Xperia 照片 | 扫描设备中的照片，根据 EXIF 中的机型（`SO-`、`SOG`、`XQ-` 等型号），找出 **用 Xperia 拍摄的 JPEG 照片** 并列出来 |
| 添加水印 | 在照片底部中央大大地合成“Taken with Xperia”标志和拍摄信息。另存为新文件，原照片保持不变 |
| 自选水印内容 | 在水印设置中，可以选择是否加入标志、拍摄机型、拍摄参数（焦距、光圈、快门速度、ISO）和拍摄时间 |
| 保存前预览 | 先确认效果，再点“为这张照片保存水印”只保存这一张 |
| 批量处理 | 支持多选、“全选”、“仅选未处理”，一次性批量合成。处理中会显示进度以及成功／出错的张数 |
| 防止重复保存 | 已经生成过水印照片的原图，在批量处理时会被安全跳过 |
| 筛选 | 列表可在“全部”“未处理”“已处理”之间切换。已处理的照片会标上“已加水印” |
| 重新扫描 | 刚拍的照片可以马上重新载入 |

### 水印包含的信息

| 项目 | 示例 |
|---|---|
| 标志 | Taken with Xperia |
| 拍摄机型 | Xperia 1 VI |
| 焦距（35mm 等效） | 24mm |
| 光圈 | F1.9 |
| 快门速度 | 1/125s |
| ISO | ISO 100 |
| 拍摄时间 | 照片的拍摄日期和时间 |

※ 示例数值仅供参考，实际会直接使用照片 EXIF 中的数值。

---

## 支持的机型

- **只要照片 EXIF 中的机型是 Xperia 的型号就支持**（`SO-`：docomo，`SOG`：au，`XQ-`：无锁版／海外版 等）。
- 与有没有蔡司镜头无关。Xperia 1／5／10 系列等，只要是 Xperia 拍的照片都可以。
- 判断依据不是“装在哪台手机上”，而是 **“照片是哪台机型拍的”**。所以只要是 Xperia 拍的照片，在其他 Android 手机上也能加水印。
- **不支持非 Xperia 拍摄的照片，以及 EXIF 已被删除的照片。**

### 与蔡司版的区别

| | Xperia All Watermark（本应用） | [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss) |
|---|---|---|
| 支持的照片 | **所有 Xperia** 拍摄的照片 | 仅蔡司 Xperia 拍摄的照片 |
| 标志 | Taken with Xperia | Xperia × ZEISS |
| 包名 | `com.aistudio.xperiawatermark.xpwm` | `com.example` |

---

## 使用方法

1. 打开应用，点“允许存储权限”，**允许** 访问照片
2. 显示“正在从存储中扫描 Xperia 照片…”之后，Xperia 拍的照片会出现在列表里
3. **只处理一张**：点照片 → 在水印预览中确认 → “为这张照片保存水印”
4. **批量处理**：选择照片（也可以“全选”或“仅选未处理”）
5. 在 **水印设置** 中选择要加入的项目
6. 点“对选中的 ○ 张批量添加水印”，一次性全部保存
7. 显示“批量处理已完成！”后，点“完成并关闭”

※ 应用界面为日语，上面的按钮名称为翻译。

保存位置为 **`Pictures/Xperia_Watermarked`**。

---

## 安装方法

1. 从 [Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest) 下载 APK
2. 点击下载好的 APK
3. 如果提示“未知来源应用”，为浏览器（或文件管理器）打开 **允许来自此来源的应用**
4. 点“安装”

> 由于不是从 Google Play 安装，可能会出现 Play 保护机制的警告。遇到时请点“详细信息”→“仍然安装”。

---

## 运行环境

| 项目 | 内容 |
|---|---|
| Android | **7.0 及以上**（API 24+） |
| 目标版本 | Android 16（API 36） |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 照片 | Xperia 拍摄的 JPEG（带 EXIF） |

---

## 使用的权限

| 权限 | 用途 |
|---|---|
| 照片和视频（`READ_MEDIA_IMAGES`） | 查找设备中的照片并添加水印（Android 13 及以上） |
| 所选照片（`READ_MEDIA_VISUAL_USER_SELECTED`） | 用于选择了“仅允许所选照片”的情况（Android 14 及以上） |
| 读取存储（`READ_EXTERNAL_STORAGE`） | 查找照片（Android 12 及以下） |
| 写入存储（`WRITE_EXTERNAL_STORAGE`） | 保存加了水印的图片（Android 9 及以下） |
| 网络（`INTERNET`、`ACCESS_NETWORK_STATE`） | 由应用内置的 Firebase 等库声明 |
| `DUMP` | 由库声明。普通应用不会被授予此权限 |

---

## 常见问题

**Q. 照片没有出现在列表里**
A. 非 Xperia 拍摄的照片，或 EXIF（拍摄信息）已被删除的照片不会显示。从社交平台保存的图片、用修图应用导出的图片，EXIF 常常已经没了。刚拍的照片请点“重新扫描”。

**Q. 会覆盖原照片吗？**
A. 不会。加了水印的图片会 **另存为新文件**，保存在 `Pictures/Xperia_Watermarked`。

**Q. 批量处理会不会把同一张照片保存好几次？**
A. 不会。已经生成过水印照片的原图，在批量处理时会自动跳过。

**Q. 能和蔡司版同时安装吗？**
A. 可以。包名不同，会作为不同的应用安装。

---

## 作者

**こねくたん（Connectan）**，又名 晓玲 清風
- 网站：https://connectan.github.io

深陷无技适国产手机坑的人。

---

## 注意

- “Xperia”是 Sony Group Corporation 的商标。
- 本应用是 **个人制作的非官方应用**，与 Sony 无关。
- 使用风险请自行承担。
