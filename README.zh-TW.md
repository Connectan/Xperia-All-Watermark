# Xperia All Watermark

[日本語](README.md) | [English](README.en.md) | [简体中文](README.zh-CN.md) | **繁體中文** | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/status-Beta%202%20(BugFix)-orange)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**一款替 Xperia 拍攝的照片加上「Taken with Xperia」標誌和拍攝資訊浮水印的 Android App。不只是蔡司（ZEISS）機型，所有 Xperia 都支援。**

App 會從照片的 EXIF 讀取機型、35mm 等效焦距、光圈、快門速度、ISO 和拍攝時間，把它們當作浮水印合成在照片底部中央，並另存成新圖片。

> 只支援蔡司 Xperia、加上「Xperia × ZEISS」標誌的版本在這裡 → [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss)

---

## ⚠️ 請先閱讀

- 這裡發布的 APK 是 **Beta 2 的 Bug 修正版**，仍然是除錯（debug）版本。
- 套件名稱為 `com.aistudio.xperiawatermark.xpwm`。它和蔡司版是不同的 App，**可以同時安裝**。
- 本 App 不透過 Google Play 發布，使用風險請自行承擔。

---

## 下載

👉 **[從 Releases 下載 APK](https://github.com/Connectan/Xperia-All-Watermark/releases/latest)**

| 項目 | 內容 |
|---|---|
| 檔名 | `XperiaAllWatermark_Beta2_BugFix_Lastest.apk` |
| 大小 | 約 22 MB |
| SHA-256 | `511b238ee9accce01bfa0c6b1e27d0bff3076be44d516956da662a3a2c6e8a6e` |

---

## 功能

| 功能 | 說明 |
|---|---|
| 自動尋找 Xperia 照片 | 掃描裝置中的照片，依 EXIF 中的機型（`SO-`、`SOG`、`XQ-` 等型號），找出 **用 Xperia 拍攝的 JPEG 照片** 並列出來 |
| 加上浮水印 | 在照片底部中央大大地合成「Taken with Xperia」標誌和拍攝資訊。另存成新檔案，原始照片保持不變 |
| 自選浮水印內容 | 在浮水印設定中，可以選擇是否加入標誌、拍攝機型、拍攝參數（焦距、光圈、快門速度、ISO）和拍攝時間 |
| 儲存前預覽 | 先確認效果，再點「為這張照片儲存浮水印」只儲存這一張 |
| 批次處理 | 支援多選、「全選」、「僅選未處理」，一次批次合成。處理中會顯示進度，以及成功／錯誤的張數 |
| 防止重複儲存 | 已經產生過浮水印照片的原圖，在批次處理時會被安全略過 |
| 篩選 | 清單可在「全部」「未處理」「已處理」之間切換。已處理的照片會標上「已加浮水印」 |
| 重新掃描 | 剛拍的照片可以馬上重新載入 |

### 浮水印包含的資訊

| 項目 | 範例 |
|---|---|
| 標誌 | Taken with Xperia |
| 拍攝機型 | Xperia 1 VI |
| 焦距（35mm 等效） | 24mm |
| 光圈 | F1.9 |
| 快門速度 | 1/125s |
| ISO | ISO 100 |
| 拍攝時間 | 照片的拍攝日期和時間 |

※ 範例數值僅供參考，實際會直接使用照片 EXIF 中的數值。

---

## 支援機型

- **只要照片 EXIF 中的機型是 Xperia 的型號就支援**（`SO-`：docomo，`SOG`：au，`XQ-`：SIM-free 版／海外版 等）。
- 與有沒有蔡司鏡頭無關。Xperia 1／5／10 系列等，只要是 Xperia 拍的照片都可以。
- 判斷依據不是「裝在哪支手機上」，而是 **「照片是哪個機型拍的」**。所以只要是 Xperia 拍的照片，在其他 Android 手機上也能加浮水印。
- **不支援非 Xperia 拍攝的照片，以及 EXIF 已被刪除的照片。**

### 與蔡司版的差異

| | Xperia All Watermark（本 App） | [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss) |
|---|---|---|
| 支援的照片 | **所有 Xperia** 拍攝的照片 | 僅蔡司 Xperia 拍攝的照片 |
| 標誌 | Taken with Xperia | Xperia × ZEISS |
| 套件名稱 | `com.aistudio.xperiawatermark.xpwm` | `com.example` |

---

## 使用方式

1. 開啟 App，點「允許儲存空間權限」，**允許** 存取照片
2. 顯示「正在從儲存空間掃描 Xperia 照片…」之後，Xperia 拍的照片會出現在清單裡
3. **只處理一張**：點照片 → 在浮水印預覽中確認 → 「為這張照片儲存浮水印」
4. **批次處理**：選擇照片（也可以「全選」或「僅選未處理」）
5. 在 **浮水印設定** 中選擇要加入的項目
6. 點「對選取的 ○ 張批次套用浮水印」，一次全部儲存
7. 顯示「批次處理完成！」後，點「完成並關閉」

※ App 介面為日文，上面的按鈕名稱為翻譯。

儲存位置為 **`Pictures/Xperia_Watermarked`**。

---

## 安裝方式

1. 從 [Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest) 下載 APK
2. 點擊下載好的 APK
3. 如果出現「不明來源的應用程式」提示，請為瀏覽器（或檔案管理 App）開啟 **允許這個來源的應用程式**
4. 點「安裝」

> 由於不是從 Google Play 安裝，可能會出現 Play 安全防護的警告。遇到時請點「詳細資料」→「仍要安裝」。

---

## 運作環境

| 項目 | 內容 |
|---|---|
| Android | **7.0 以上**（API 24+） |
| 目標版本 | Android 16（API 36） |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 照片 | Xperia 拍攝的 JPEG（含 EXIF） |

---

## 使用的權限

| 權限 | 用途 |
|---|---|
| 相片和影片（`READ_MEDIA_IMAGES`） | 尋找裝置中的照片並加上浮水印（Android 13 以上） |
| 所選相片（`READ_MEDIA_VISUAL_USER_SELECTED`） | 用於選擇了「僅允許所選相片」的情況（Android 14 以上） |
| 讀取儲存空間（`READ_EXTERNAL_STORAGE`） | 尋找照片（Android 12 以下） |
| 寫入儲存空間（`WRITE_EXTERNAL_STORAGE`） | 儲存加上浮水印的圖片（Android 9 以下） |
| 網路（`INTERNET`、`ACCESS_NETWORK_STATE`） | 由 App 內建的 Firebase 等函式庫宣告 |
| `DUMP` | 由函式庫宣告。一般 App 不會被授予此權限 |

---

## 常見問題

**Q. 照片沒有出現在清單裡**
A. 非 Xperia 拍攝的照片，或 EXIF（拍攝資訊）已被刪除的照片不會顯示。從社群平台儲存的圖片、用修圖 App 匯出的圖片，EXIF 常常已經不見了。剛拍的照片請點「重新掃描」。

**Q. 會覆蓋原始照片嗎？**
A. 不會。加上浮水印的圖片會 **另存成新檔案**，儲存在 `Pictures/Xperia_Watermarked`。

**Q. 批次處理會不會把同一張照片儲存好幾次？**
A. 不會。已經產生過浮水印照片的原圖，在批次處理時會自動略過。

**Q. 能和蔡司版同時安裝嗎？**
A. 可以。套件名稱不同，會當作不同的 App 安裝。

---

## 作者

**こねくたん（Connectan）**，又名 晓玲 清風
- 網站：https://connectan.github.io

深陷無技適中國手機坑的人。

---

## 注意

- 「Xperia」是 Sony Group Corporation 的商標。
- 本 App 是 **個人製作的非官方 App**，與 Sony 無關。
- 使用風險請自行承擔。
