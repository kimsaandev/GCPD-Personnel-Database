# GCPD Personnel Database

> **Dark Knight Rises 스타일 첩보 UI 기반 인물 이력서 뷰어**  
> 단일 HTML 파일 + 사진 이미지만으로 동작하는 바이오메트릭 인물 데이터베이스

---

## 📸 Preview

![Demo](demo.gif)

---

## ✨ 주요 기능

### 바이오메트릭 HUD 오버레이
인물 사진 선택 시 첩보영화 스타일 스캔 시퀀스가 자동 실행됩니다.

- 얼굴 감지 박스 (코너 브래킷) 등장
- EYE_L / EYE_R / NOSE / MOUTH 바이오메트릭 랜드마크 포인트 순차 출현
- 수직 스캔라인 sweep 애니메이션
- `▶ MATCH FOUND ◀` 확인 메시지 및 99.7% 컨피던스 바

### 지문 스캐너 패널 (우측)
인물마다 고유한 지문 패턴을 Canvas API로 실시간 생성합니다.

- 동심 타원 지문 패턴
- Delaunay 삼각망 오버레이
- 실시간 스캔 스윕 애니메이션
- 좌표 / 줌 레벨 데이터 표시

### 실시간 스캔 로그
인물 선택 시 분석 진행 과정을 순차 애니메이션으로 시뮬레이션합니다.

### 인물 검색 및 필터
이름 / 직책 / 부서 / 스킬 키워드 실시간 필터링

### CSV 로드
좌하단 `▼ LOAD CSV RECORD` 버튼으로 외부 CSV 파일을 로드해  
원하는 인물 데이터로 교체할 수 있습니다.

### CRT 모니터 효과
스캔라인 오버레이 / 비네팅 / 그린 포스포 팔레트로 영화 UI 분위기 재현

---

## 📁 파일 구조

```
gotham-db/
├── index.html   ← 메인 파일 (단일 HTML, 외부 라이브러리 의존 없음)
├── 1.png        ← 1번 인물 사진
├── 2.png        ← 2번 인물 사진
├── 3.png        ← 3번 인물 사진
├── 4.png        ← 4번 인물 사진
├── 5.png        ← 5번 인물 사진
├── 6.png        ← 6번 인물 사진
├── 7.png        ← 7번 인물 사진
├── 8.png        ← 8번 인물 사진
└── README.md
```

---

## 🚀 실행 방법

> ⚠️ `file://` 직접 실행 시 이미지 CORS 오류가 발생할 수 있습니다.  
> 반드시 **로컬 HTTP 서버**를 통해 실행하세요.

```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .

# VS Code
# Live Server 익스텐션 → index.html 우클릭 → Open with Live Server
```

브라우저에서 `http://localhost:8080` 접속

---

## 🖼️ 사진 설정

`1.png` ~ `8.png` 파일을 `index.html`과 **같은 폴더**에 배치하면 자동 적용됩니다.  
사진이 없으면 `NO PHOTO ON FILE` placeholder가 표시됩니다.

| 항목 | 권장 사양 |
|------|-----------|
| 파일명 | `1.png` ~ `8.png` (고정) |
| 포맷 | `.png` / `.jpg` 모두 가능 |
| 비율 | 세로형 권장 (3:4 또는 2:3) |
| 피사체 | 인물 상반신 위주, 정면 촬영 |

---

## 📋 CSV 포맷

### 컬럼 스펙

| 컬럼 | 타입 | 설명 |
|------|------|------|
| `name` | string | 이름 |
| `position` | string | 직책 |
| `department` | string | 부서명 |
| `dob` | `YYYY-MM-DD` | 생년월일 |
| `nationality` | string | 국적 코드 (예: `KOR`) |
| `height` | number | 신장 (cm) |
| `contact` | string | 이메일 주소 |
| `years_exp` | number | 총 경력 연수 |
| `skills` | string | 기술 스택 — 쉼표 구분, **따옴표로 감쌀 것** |
| `history` | string | 경력 — `기간:조직:직책` 형식, 쉼표 구분, **따옴표로 감쌀 것** |
| `projects` | string | 주요 프로젝트 — 쉼표 구분, **따옴표로 감쌀 것** |
| `notes` | string | 특이사항 / 메모 |

### 경력(`history`) 포맷

```
"2018-2020:회사A:Junior Designer,2020-2022:회사B:Lead Designer,2022-Present:회사C:Director"
```

- 각 항목: `시작연도-종료연도:조직명:직책`
- 항목 구분: `,` (쉼표)
- 전체를 `"` 따옴표로 감쌀 것

### 전체 템플릿

```csv
name,position,department,dob,nationality,height,contact,years_exp,skills,history,projects,notes
홍길동,Senior Developer,R&D Division,1990-05-12,KOR,178,hong@gmail.com,8,"Python,Unity,WebGL","2018-2020:스튜디오A:Developer,2020-Present:스튜디오B:Lead","프로젝트A,프로젝트B","풀스택 개발자. 오픈소스 컨트리뷰터."
```

---

## 🛠️ 기술 스택

| 항목 | 내용 |
|------|------|
| 언어 | HTML / CSS / Vanilla JS |
| 렌더링 | Canvas API (지문 스캐너) |
| 애니메이션 | CSS Animation + requestAnimationFrame |
| 폰트 | Google Fonts (Share Tech Mono, Oswald, Rajdhani, VT323) |
| 외부 의존성 | **없음** — 단일 HTML 파일로 완결 |

---

## 🎨 디자인 레퍼런스

- *The Dark Knight Rises* (2012) — GCPD / Wayne Enterprises Applied Sciences Division UI
- 첩보영화 바이오메트릭 스캔 HUD 인터페이스
- CRT 그린 포스포 터미널 미학

---

## 📄 License

MIT License — 자유롭게 사용, 수정, 배포 가능합니다.
