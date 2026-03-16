<div align="center">

```
╔═══════════════════════════════════════════════════════╗
║  FBI FINGERPRINT DATABASE  //  GCPD NODE-04           ║
║  CLASSIFICATION : RESTRICTED   AUTH : LVL-3           ║
║  SESSION : ACTIVE              ENC  : AES-256         ║
╚═══════════════════════════════════════════════════════╝
```

# GCPD Personnel Database

**Biometric Intelligence UI — Spy Film Grade Interface**  
**바이오메트릭 인텔리전스 UI — 첩보영화 수준의 인터페이스**

[![HTML](https://img.shields.io/badge/HTML-Single%20File-2e5028?style=flat-square&logo=html5)](.)
[![CSS](https://img.shields.io/badge/CSS-Vanilla-2e5028?style=flat-square&logo=css3)](.)
[![JS](https://img.shields.io/badge/JS-Vanilla-2e5028?style=flat-square&logo=javascript)](.)
[![License](https://img.shields.io/badge/License-MIT-4a8038?style=flat-square)](.)

</div>

---

## 📡 Overview / 개요

**EN**  
A single-file personnel viewer that replicates the kind of intelligence terminal UI seen in blockbuster spy films — think *The Dark Knight Rises*, *Mission Impossible*, *Minority Report*. Load a CSV, drop in portrait photos, and your team roster becomes a classified government database. No frameworks. No build tools. Just one HTML file.

**KO**  
*다크 나이트 라이즈*, *미션 임파서블*, *마이너리티 리포트* 같은 첩보 블록버스터에서 볼 법한 인텔리전스 터미널 UI를 구현한 단일 파일 인물 뷰어입니다. CSV를 로드하고 인물 사진을 폴더에 넣으면, 평범한 팀 명단이 기밀 정부 데이터베이스로 변환됩니다. 프레임워크도, 빌드 툴도 없습니다. HTML 파일 하나로 완결됩니다.

---

## 🎬 Film-Grade Features / 영화급 기능

### `[01]` Biometric Scan Sequence / 바이오메트릭 스캔 시퀀스

**EN**  
Every time you select a subject, the system runs a full facial recognition sequence — exactly the kind you'd see on a CIA analyst's screen.

**KO**  
인물을 선택할 때마다 CIA 분석관의 화면에서 볼 법한 얼굴 인식 시퀀스가 자동 실행됩니다.

```
1. Corner bracket targeting reticle appears
2. Face detection box locks onto subject
3. Biometric landmark points materialize — EYE_L / EYE_R / NOSE / MOUTH
4. Vertical scan-line sweeps the frame
5. "▶ MATCH FOUND ◀" confirmation with 99.7% confidence bar
```

---

### `[02]` Fingerprint Scanner Panel / 지문 스캐너 패널

**EN**  
The right panel renders a unique fingerprint visualization per subject using Canvas API — concentric ellipse whorls overlaid with a Delaunay triangulation mesh and a live sweep animation. Every subject gets a procedurally distinct pattern.

**KO**  
우측 패널은 Canvas API로 인물마다 고유한 지문 시각화를 실시간 생성합니다. 동심 타원 지문 패턴 위에 Delaunay 삼각망이 오버레이되고 스캔 스윕 애니메이션이 반복됩니다. 모든 인물이 절차적으로 구별되는 고유 패턴을 가집니다.

---

### `[03]` CRT Terminal Aesthetic / CRT 터미널 미학

**EN**  
Scanline overlay, radial vignette, and a pure phosphor-green palette combine to recreate the authentic feel of a classified government workstation — not a website pretending to be one.

**KO**  
스캔라인 오버레이, 방사형 비네팅, 순수 포스포 그린 팔레트가 결합되어 기밀 정부 워크스테이션의 질감을 재현합니다. 흉내 내는 웹사이트가 아닌, 실제처럼 느껴지는 UI입니다.

---

### `[04]` Live Scan Log & ID Results / 실시간 스캔 로그 & ID 결과

**EN**  
A real-time terminal log streams analysis steps with sequential timing, mirroring the data-processing readouts in modern spy thrillers. Identification results populate in the adjacent column as the scan completes.

**KO**  
실시간 터미널 로그가 분석 단계를 순차적으로 스트리밍하며, 현대 스파이 스릴러의 데이터 처리 화면을 재현합니다. 스캔이 완료되면 옆 컬럼에 신원 확인 결과가 채워집니다.

---

### `[05]` Live Search & CSV Loader / 실시간 검색 & CSV 로더

**EN**  
Filter subjects in real time by name, position, department, or skill. Load any CSV to replace the demo dataset — turn this into a company directory, event roster, or fictional intel dossier.

**KO**  
이름, 직책, 부서, 스킬로 인물을 실시간 필터링합니다. CSV를 로드해 데모 데이터를 교체하면 회사 디렉터리, 이벤트 명단, 또는 픽션 인텔 도시에로 활용할 수 있습니다.

---

## 📁 File Structure / 파일 구조

```
gotham-db/
├── index.html        ← Single entry point. No build required.
│                       단일 진입점. 빌드 불필요.
│
├── 1.png             ← Subject 01 portrait photo / 1번 인물 사진
├── 2.png             ← Subject 02 portrait photo / 2번 인물 사진
├── 3.png             ← Subject 03 portrait photo / 3번 인물 사진
├── 4.png             ← Subject 04 portrait photo / 4번 인물 사진
├── 5.png             ← Subject 05 portrait photo / 5번 인물 사진
├── 6.png             ← Subject 06 portrait photo / 6번 인물 사진
├── 7.png             ← Subject 07 portrait photo / 7번 인물 사진
├── 8.png             ← Subject 08 portrait photo / 8번 인물 사진
│
└── README.md
```

---

## 🚀 Quickstart / 빠른 시작

> ⚠️ **EN:** Opening via `file://` may block image loading due to CORS.  
> ⚠️ **KO:** `file://` 직접 실행 시 CORS로 인해 이미지 로드가 차단될 수 있습니다.  
> Always serve through a local HTTP server. / 반드시 로컬 HTTP 서버를 통해 실행하세요.

```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .

# VS Code — Live Server extension
# index.html 우클릭 → Open with Live Server
```

Open `http://localhost:8080` in your browser.

---

## 🖼️ Photo Setup / 사진 설정

Place `1.png` through `8.png` in the **same directory as `index.html`**.  
`index.html`과 **같은 폴더**에 `1.png` ~ `8.png`를 배치하세요.

If a photo is missing, `NO PHOTO ON FILE` placeholder is shown.  
사진이 없으면 `NO PHOTO ON FILE` placeholder가 표시됩니다.

| | EN | KO |
|---|---|---|
| **Filename** | `1.png` ~ `8.png` (fixed) | 고정 파일명 |
| **Format** | `.png` or `.jpg` both work | `.png` / `.jpg` 모두 가능 |
| **Ratio** | Portrait preferred (3:4 or 2:3) | 세로형 권장 |
| **Subject** | Upper body, front-facing | 상반신, 정면 |

---

## 📋 CSV Format / CSV 포맷

### Column Spec / 컬럼 스펙

| Column | Type | EN | KO |
|--------|------|----|----|
| `name` | string | Full name | 이름 |
| `position` | string | Job title | 직책 |
| `department` | string | Department | 부서명 |
| `dob` | `YYYY-MM-DD` | Date of birth | 생년월일 |
| `nationality` | string | Country code e.g. `KOR` | 국적 코드 |
| `height` | number | Height in cm | 신장 (cm) |
| `contact` | string | Email address | 이메일 |
| `years_exp` | number | Years of experience | 경력 연수 |
| `skills` | string | Comma-separated, **wrap in quotes** | 쉼표 구분, **따옴표 필수** |
| `history` | string | `period:org:role` comma-separated, **wrap in quotes** | `기간:조직:직책` 형식, **따옴표 필수** |
| `projects` | string | Comma-separated, **wrap in quotes** | 쉼표 구분, **따옴표 필수** |
| `notes` | string | Free-text notes | 비고 |

### `history` Field Format

```
"2018-2020:Organization A:Junior Role,2020-2022:Organization B:Senior Role,2022-Present:Organization C:Lead"
```

### Full Template / 전체 템플릿

```csv
name,position,department,dob,nationality,height,contact,years_exp,skills,history,projects,notes
홍길동,Senior Developer,R&D Division,1990-05-12,KOR,178,hong@gmail.com,8,"Python,Unity,WebGL","2018-2020:Studio A:Developer,2020-Present:Studio B:Lead","Project A,Project B","Full-stack developer and open source contributor."
```

---

## 🛠️ Tech Stack / 기술 스택

| | EN | KO |
|---|---|---|
| **Language** | HTML / CSS / Vanilla JS | 순수 웹 표준 |
| **Rendering** | Canvas API — fingerprint scanner | 지문 스캐너 시각화 |
| **Animation** | CSS Animation + `requestAnimationFrame` | HUD / 스캔 시퀀스 |
| **Fonts** | Google Fonts — Share Tech Mono, Oswald, Rajdhani, VT323 | |
| **Dependencies** | **None.** Single HTML file. | **없음.** 단일 HTML 파일. |

---

## 🎞️ Design References / 디자인 레퍼런스

| Film / 영화 | UI Element Referenced / 참조 요소 |
|---|---|
| *The Dark Knight Rises* (2012) | GCPD / Wayne Enterprises Applied Sciences terminal |
| *Mission: Impossible* series | Biometric scan HUD overlays |
| *Minority Report* (2002) | Gestural data interface aesthetics |
| *Enemy of the State* (1998) | Surveillance database readouts |
| *Jack Ryan* (Amazon series) | CIA analyst workstation layout |

---

## 📄 License / 라이선스

```
MIT License

EN : Free to use, modify, and distribute.
KO : 자유롭게 사용, 수정, 배포 가능합니다.
```

---

<div align="center">

```
[ GCPD APPLIED SCIENCES // CLEARANCE LVL-3 // AUTHORIZED PERSONNEL ONLY ]
```

</div>
