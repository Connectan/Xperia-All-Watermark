# Xperia All Watermark

[日本語](README.md) | [English](README.en.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | **한국어**

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/status-Beta%202%20(BugFix)-orange)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**Xperia로 찍은 사진에 "Taken with Xperia" 로고와 촬영 정보 워터마크를 넣는 Android 앱입니다. ZEISS 탑재 모델뿐 아니라 모든 Xperia를 지원합니다.**

사진의 EXIF에서 기종명, 35mm 환산 초점 거리, F값, 셔터 속도, ISO, 촬영 일시를 읽습니다. 이를 사진 하단 중앙에 워터마크로 합성해 새 이미지로 저장합니다.

> ZEISS 탑재 Xperia 전용으로 "Xperia × ZEISS" 로고를 넣는 버전은 여기 → [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss)

---

## ⚠️ 먼저 읽어 주세요

- 배포 중인 APK는 **Beta 2의 버그 수정판** 입니다. 아직 디버그 빌드입니다.
- 패키지명은 `com.aistudio.xperiawatermark.xpwm` 입니다. ZEISS 버전과는 다른 앱이라서 **둘 다 동시에 설치할 수 있습니다**.
- Google Play 외부에서 배포하는 앱입니다. 사용은 본인 책임입니다.

---

## 다운로드

👉 **[Releases에서 APK 다운로드](https://github.com/Connectan/Xperia-All-Watermark/releases/latest)**

| 항목 | 내용 |
|---|---|
| 파일명 | `XperiaAllWatermark_Beta2_BugFix_Lastest.apk` |
| 크기 | 약 22 MB |
| SHA-256 | `511b238ee9accce01bfa0c6b1e27d0bff3076be44d516956da662a3a2c6e8a6e` |

---

## 주요 기능

| 기능 | 내용 |
|---|---|
| Xperia 사진 자동 탐색 | 기기 안의 사진을 스캔합니다. EXIF의 기종명(`SO-`, `SOG`, `XQ-` 등의 모델 번호)으로 **Xperia로 찍은 JPEG 사진** 을 찾아 목록으로 보여 줍니다 |
| 워터마크 넣기 | "Taken with Xperia" 로고와 촬영 정보를 사진 하단 중앙에 크게 합성합니다. 별도 파일로 저장하므로 원본 사진은 그대로입니다 |
| 넣을 항목 선택 | 워터마크 설정에서 로고, 촬영 기종, 촬영 파라미터(초점 거리, 조리개 값, 셔터 속도, ISO), 촬영 일시를 넣을지 고를 수 있습니다 |
| 저장 전 미리보기 | 결과를 확인한 뒤 "이 사진에 워터마크 저장"으로 그 사진만 저장할 수 있습니다 |
| 일괄 처리 | 다중 선택, "모두 선택", "미처리만 선택"으로 한 번에 합성합니다. 처리 중에는 진행 상황과 성공／오류 장수가 표시됩니다 |
| 중복 저장 방지 | 이미 워터마크 사진을 만든 사진은 일괄 처리 때 안전하게 건너뜁니다 |
| 필터 | "전체", "미처리", "처리 완료"로 목록을 전환할 수 있습니다. 처리한 사진에는 "워터마크 완료" 표시가 붙습니다 |
| 다시 스캔 | 방금 찍은 사진을 바로 다시 불러올 수 있습니다 |

### 워터마크에 들어가는 정보

| 항목 | 예시 |
|---|---|
| 로고 | Taken with Xperia |
| 촬영 기종 | Xperia 1 VI |
| 초점 거리(35mm 환산) | 24mm |
| F값 | F1.9 |
| 셔터 속도 | 1/125s |
| ISO | ISO 100 |
| 촬영 일시 | 사진을 찍은 날짜와 시간 |

※ 예시 값은 참고용입니다. 실제로는 사진 EXIF에 들어 있는 값이 그대로 사용됩니다.

---

## 지원 기종

- **사진 EXIF의 기종명이 Xperia 모델 번호라면 지원** 합니다(`SO-`: docomo, `SOG`: au, `XQ-`: 자급제·해외판 등).
- ZEISS 렌즈 유무와는 관계없습니다. Xperia 1／5／10 시리즈 등 Xperia로 찍은 사진이라면 모두 대상입니다.
- 판정은 "어느 기기에 설치했는지"가 아니라 **"어느 기종으로 찍은 사진인지"** 로 합니다. 그래서 Xperia로 찍은 사진이라면 다른 Android 기기에서도 워터마크를 넣을 수 있습니다.
- **Xperia 이외의 기기로 찍은 사진이나 EXIF가 지워진 사진에는 사용할 수 없습니다.**

### ZEISS 버전과의 차이

| | Xperia All Watermark(이 앱) | [Xperia Watermark For Zeiss](https://github.com/Connectan/Xperia-Watermark-For-Zeiss) |
|---|---|---|
| 대상 사진 | **모든 Xperia** 로 찍은 사진 | ZEISS 탑재 Xperia로 찍은 사진만 |
| 로고 | Taken with Xperia | Xperia × ZEISS |
| 패키지명 | `com.aistudio.xperiawatermark.xpwm` | `com.example` |

---

## 사용 방법

1. 앱을 열고 "저장소 권한 허용"에서 사진 접근을 **허용** 합니다
2. "저장소에서 Xperia 사진을 스캔하는 중…" 이후 Xperia로 찍은 사진이 목록에 나타납니다
3. **한 장만** 처리할 때: 사진을 탭 → 워터마크 미리보기에서 확인 → "이 사진에 워터마크 저장"
4. **여러 장** 처리할 때: 사진을 선택합니다("모두 선택", "미처리만 선택"도 있습니다)
5. **워터마크 설정** 에서 넣고 싶은 항목을 고릅니다
6. "선택한 ○장에 워터마크 일괄 적용"을 누르면 한 번에 저장됩니다
7. "일괄 처리가 완료되었습니다!"가 나오면 "완료하고 닫기"

※ 앱 화면은 일본어입니다. 위의 버튼 이름은 번역한 것입니다.

저장 위치는 **`Pictures/Xperia_Watermarked`** 입니다.

---

## 설치 방법

1. [Releases](https://github.com/Connectan/Xperia-All-Watermark/releases/latest)에서 APK 다운로드
2. 다운로드한 APK를 탭
3. "출처를 알 수 없는 앱" 허용을 요청하면 브라우저(또는 파일 앱)의 **이 출처 허용** 을 켭니다
4. "설치"를 누릅니다

> Google Play 외부에서 설치하는 것이라 Play 프로텍트 경고가 나올 수 있습니다. 그럴 때는 "세부정보" → "무시하고 설치"로 진행해 주세요.

---

## 동작 환경

| 항목 | 내용 |
|---|---|
| Android | **7.0 이상**(API 24+) |
| 타깃 | Android 16(API 36) |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 사진 | Xperia로 찍은 JPEG(EXIF 포함) |

---

## 사용하는 권한

| 권한 | 용도 |
|---|---|
| 사진 및 동영상(`READ_MEDIA_IMAGES`) | 기기 안의 사진을 찾아 워터마크를 넣기 위해(Android 13 이상) |
| 선택한 사진(`READ_MEDIA_VISUAL_USER_SELECTED`) | "선택한 사진만 허용"을 골랐을 때를 위해(Android 14 이상) |
| 저장소 읽기(`READ_EXTERNAL_STORAGE`) | 사진을 찾기 위해(Android 12 이하) |
| 저장소 쓰기(`WRITE_EXTERNAL_STORAGE`) | 워터마크를 넣은 이미지를 저장하기 위해(Android 9 이하) |
| 인터넷(`INTERNET`, `ACCESS_NETWORK_STATE`) | 앱에 포함된 Firebase 등의 라이브러리가 선언한 것 |
| `DUMP` | 라이브러리에서 선언한 것입니다. 일반 앱에는 부여되지 않는 권한입니다 |

---

## 자주 묻는 질문

**Q. 사진이 목록에 나오지 않아요**
A. Xperia 이외의 기기로 찍은 사진이나 EXIF(촬영 정보)가 지워진 사진은 나오지 않습니다. SNS에서 저장한 이미지나 편집 앱에서 내보낸 이미지는 EXIF가 지워져 있는 경우가 많습니다. 방금 찍은 사진은 "다시 스캔"으로 다시 불러와 주세요.

**Q. 원본 사진이 덮어쓰기 되나요?**
A. 아닙니다. 워터마크를 넣은 이미지는 **별도 파일로** `Pictures/Xperia_Watermarked`에 저장됩니다.

**Q. 일괄 처리로 같은 사진을 여러 번 저장하지는 않나요?**
A. 괜찮습니다. 이미 워터마크 사진을 만든 사진은 일괄 처리 때 자동으로 건너뜁니다.

**Q. ZEISS 버전과 함께 설치할 수 있나요?**
A. 가능합니다. 패키지명이 달라서 별개의 앱으로 설치됩니다.

---

## 만든 사람

**こねくたん(Connectan)**, 晓玲 清風
- 사이트: https://connectan.github.io

일본 미인증 중국폰 늪의 주민.

---

## 주의

- "Xperia"는 Sony Group Corporation의 상표입니다.
- 이 앱은 **개인이 만든 비공식 앱** 이며 Sony와는 관계가 없습니다.
- 사용은 본인 책임입니다.
