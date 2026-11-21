# Xperia All Watermark

**日本語** | [English](README.en.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/status-Beta%202%20(BugFix)-orange)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**Xperia で撮った写真に、「Taken with Xperia」ロゴと撮影情報の透かしを入れる Android アプリです。ZEISS 搭載モデルだけでなく、すべての Xperia に対応しています。**

写真の EXIF から、機種名・35mm 換算の焦点距離・F 値・シャッタースピード・ISO・撮影日時を読み取ります。それを写真の中央下部に透かしとして合成し、新しい画像として保存します。

> ZEISS 搭載 Xperia 専用で、「Xperia × ZEISS」ロゴを入れる版はこちら → [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss)

---

## ⚠️ 最初に読んでね

- 配布している APK は **Beta 2 のバグ修正版** です。デバッグビルドのままです。
- パッケージ名は `com.aistudio.xperiawatermark.xpwm` です。ZEISS 版とは別アプリなので **両方同時にインストールできます**。
- Google Play 以外からの配布です。使用は自己責任でお願いします。

---

## ダウンロード

👉 **[Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest) から APK をダウンロード**

| 項目 | 内容 |
|---|---|
| ファイル名 | `XperiaAllWatermark_Beta2_BugFix_Lastest.apk` |
| サイズ | 約 22 MB |
| SHA-256 | `511b238ee9accce01bfa0c6b1e27d0bff3076be44d516956da662a3a2c6e8a6e` |

---

## できること

| 機能 | 内容 |
|---|---|
| Xperia の写真を自動で探す | 端末内の写真をスキャンします。EXIF の機種名（`SO-`・`SOG`・`XQ-` などの型番）から、**Xperia で撮った JPEG 写真** を見つけて一覧にします |
| 透かしを入れる | 「Taken with Xperia」ロゴと撮影情報を、写真の中央下部に大きく合成します。保存は別ファイルなので、元の写真はそのままです |
| 入れる項目を選べる | ウォーターマーク設定で、ロゴ・撮影機種・撮影パラメータ（焦点距離・絞り値・シャッタースピード・ISO）・撮影日時を入れるかどうかを選べます |
| 保存前にプレビュー | 仕上がりを確認してから、「この写真に透かしを保存」でその写真だけ保存できます |
| まとめて処理 | 複数選択・「すべて選択」・「未処理のみ選択」で一括合成できます。処理中は進み具合と、成功／エラーの枚数が出ます |
| 重複保存を防止 | すでに透かし写真を作った写真は、一括処理のときに安全にスキップされます |
| 絞り込み | 「すべて」「未処理」「処理済」で一覧を切り替えられます。処理済みの写真には「透かし済」の印が付きます |
| 再スキャン | 新しく撮った写真をすぐ読み込み直せます |

### 透かしに入る情報

| 項目 | 例 |
|---|---|
| ロゴ | Taken with Xperia |
| 撮影機種 | Xperia 1 VI |
| 焦点距離（35mm 換算） | 24mm |
| F 値 | F1.9 |
| シャッタースピード | 1/125s |
| ISO | ISO 100 |
| 撮影日時 | 撮影した日付・時刻 |

※ 例の数値はイメージです。実際は写真の EXIF に入っている値がそのまま使われます。

---

## 対応機種

- **写真の EXIF の機種名が Xperia の型番になっていれば対応** しています（`SO-`：docomo、`SOG`：au、`XQ-`：SIM フリー・海外版 など）。
- ZEISS レンズの有無は関係ありません。Xperia 1 / 5 / 10 シリーズなど、Xperia で撮った写真ならすべて対象です。
- 判定は「どの端末にインストールしたか」ではなく **「どの機種で撮った写真か」** で行います。なので、Xperia で撮った写真なら、ほかの Android 端末でも透かしを入れられます。
- **Xperia 以外で撮った写真や、EXIF が消えている写真には使えません。**

---

## 使い方

1. アプリを開いて、「ストレージ権限を許可する」から写真へのアクセスを **許可** します
2. 「ストレージから Xperia 写真をスキャン中…」のあと、Xperia で撮った写真が一覧に出ます
3. **1枚だけ** なら：写真をタップ → 透かし合成プレビューで確認 → 「この写真に透かしを保存」
4. **まとめて** なら：写真を選ぶ（「すべて選択」「未処理のみ選択」もあります）
5. **ウォーターマーク設定** で、入れたい項目を選びます
6. 「選択した ○ 枚に透かしを一括適用」を押すと、まとめて保存されます
7. 「一括処理が完了しました！」と出たら「完了して閉じる」

保存先は **`Pictures/Xperia_Watermarked`** です。

---

## インストール方法

1. [Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest) から APK をダウンロード
2. ダウンロードした APK をタップ
3. 「提供元不明のアプリ」の許可を求められたら、ブラウザ（またはファイルアプリ）の **このソースからのアプリを許可** をオンにする
4. 「インストール」を押す

> Google Play 以外からのインストールなので、Play プロテクトの警告が出ることがあります。その場合は「詳細」→「インストールする」で進めてください。

---

## 動作環境

| 項目 | 内容 |
|---|---|
| Android | **7.0 以上**（API 24〜） |
| ターゲット | Android 16（API 36） |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 写真 | Xperia で撮った JPEG（EXIF 付き） |

---

## 使う権限

| 権限 | 何に使うか |
|---|---|
| 写真と動画へのアクセス（`READ_MEDIA_IMAGES`） | 端末内の写真を探して、透かしを入れるため（Android 13 以降） |
| 選択した写真へのアクセス（`READ_MEDIA_VISUAL_USER_SELECTED`） | 「選択した写真のみ許可」を選んだときのため（Android 14 以降） |
| ストレージの読み取り（`READ_EXTERNAL_STORAGE`） | 写真を探すため（Android 12 以前） |
| ストレージへの書き込み（`WRITE_EXTERNAL_STORAGE`） | 透かし入り画像を保存するため（Android 9 以前） |
| インターネット（`INTERNET`・`ACCESS_NETWORK_STATE`） | アプリに含まれている Firebase などのライブラリが宣言しているもの |
| `DUMP` | ライブラリ由来の宣言です。通常のアプリには付与されない権限です |

---

## よくある質問

**Q. 写真が一覧に出てこない**
A. Xperia 以外で撮った写真や、EXIF（撮影情報）が消えている写真は出てきません。SNS から保存した画像や、編集アプリで書き出した画像は EXIF が消えていることが多いです。撮ったばかりの写真は「再スキャン」で読み込み直してください。

**Q. 元の写真は上書きされる？**
A. されません。透かし入りの画像を **別のファイルとして** `Pictures/Xperia_Watermarked` に保存します。

**Q. 同じ写真を一括処理で何度も保存しちゃわない？**
A. 大丈夫です。すでに透かし写真を作った写真は、一括処理のときに自動でスキップされます。

**Q. ZEISS 版と一緒に入れられる？**
A. 入れられます。パッケージ名が違うので、別のアプリとしてインストールされます。

---

## 作った人

**こねくたん**（晓玲 清風）
- サイト：https://connectan.github.io

技適なし中華スマホ沼の住人。

---

## 注意

- 「Xperia」は Sony Group Corporation の商標です。
- このアプリは **個人が作った非公式アプリ** で、Sony とは関係ありません。
- 使用は自己責任でお願いします。
