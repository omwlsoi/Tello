<!-- TODO: 아래 src에 이미 올린 로고 이미지 링크 붙여넣기 -->
<p align="center">
  <img src="여기에_로고_이미지_링크" width="400" />
</p>

<div align="center">

# Tello 텔로

**매장 QR을 찍으면, 내 폰이 배리어프리 키오스크가 됩니다.**

[📹 시연 영상](#-시연-영상) · [💻 프론트엔드 레포](https://github.com/omwlsoi/tello-front) · [🛠 백엔드 레포](https://github.com/yedamimi/tello-backend)

</div>

<br/>

## 🌱 프로젝트 소개

2026년 1월 28일부터 <b>배리어프리 키오스크 설치·운영 의무</b>가 전면 시행되었습니다.

하지만 배리어프리 키오스크는 일반 기기의 <b>약 2배 가격</b>이라 소상공인에게 큰 부담이고,
기계를 바꿔도 시각장애인의 <b>72.3%</b>, 휠체어 이용자의 <b>61.5%</b>는 여전히 직원 도움을 선호합니다.
<b>기계만 바꾼다고 불편이 사라지지는 않았습니다.</b>

Tello는 반대로 접근합니다.
모두에게 맞는 기계 하나를 새로 들이는 대신, 이용자에게 가장 익숙한 <b>내 폰</b>을 키오스크로 바꿉니다.

> 🧓 키오스크가 어려운 <b>고령층</b>, 👧 혼자 주문해 보고 싶은 <b>어린이</b>도
> 뒷사람 눈치 없이, 내 폰으로, <b>말로</b> 주문할 수 있도록.

| 이용자 | 사장님 | 사회 |
|---|---|---|
| 남의 도움 없이 혼자 주문 | 기기 교체 없이 배리어프리 의무 대응 | 형식적 설치가 아닌 실제 접근성으로 |

<br/>

## ✨ 핵심 기능

### 1. 🎙️ 대화형 음성 주문
"아아 하나, 얼음 적게"처럼 평소 말투로 말하면 AI 캐릭터 <b>텔로링</b>이 메뉴·수량·옵션을 알아듣습니다.
빠진 옵션은 다시 물어보고, 주문 내용을 음성으로 읽어주며 확인합니다.
옵션은 <b>버튼</b>으로 눌러도, <b>마이크</b>로 말해도 답할 수 있습니다.

### 2. 📱 내 폰 = 키오스크
매장에 붙은 QR을 찍으면 <b>앱 설치 없이</b> 웹으로 바로 열립니다.
폰에 이미 설정된 글씨 크기·화면 읽기 기능을 그대로 함께 쓸 수 있습니다.

### 3. 🔠 큰글씨 모드
상단 <b>X2</b> 버튼 하나로 화면 전체 글씨가 2배로 커집니다.

### 4. 🙋 막혔을 때만 나타나는 직원 호출
처음부터 직원 호출을 강요하지 않고, 오류가 나거나 진행이 막혔을 때만 직원 부르기 버튼을 보여줍니다.
음성 주문과 터치 주문은 <b>같은 장바구니</b>를 사용해 언제든 방식을 바꿀 수 있습니다.

### 5. 🧑‍🍳 사장님 화면
들어온 주문과 직원 호출 요청을 사장님 전용 화면(`/boss`)에서 한눈에 확인하고 처리합니다.

<br/>

## 📱 화면 미리보기

<!-- TODO: 스크린샷 넣기 (README 편집창에 이미지 드래그 → 생성된 링크를 src에 붙여넣기) -->
| QR 진입 | 메뉴 | 음성 주문 | 주문 확인 | 주문 현황 |
|:---:|:---:|:---:|:---:|:---:|
| <img src="" width="160"/> | <img src="" width="160"/> | <img src="" width="160"/> | <img src="" width="160"/> | <img src="" width="160"/> |

| 기본 모드 | 큰글씨 모드 (X2) | 사장님 화면 |
|:---:|:---:|:---:|
| <img src="" width="160"/> | <img src="" width="160"/> | <img src="" width="160"/> |

<br/>

## 📹 시연 영상

<!-- TODO: 영상 파일을 README 편집창에 드래그하면 자동으로 링크가 생겨요 -->

<br/>

## 🔁 서비스 흐름

```
📷 매장 QR 스캔
   ↓
🌐 웹 주문 화면 실행 (앱 설치 X)
   ↓
🎙️ 음성 · 터치로 주문
   ↓  음성 → STT(Web Speech API) → LLM(Gemini가 메뉴·수량·옵션 파악) → TTS(음성 안내)
   ↓
✅ 텔로링이 주문 내용 읽어주기 → 이용자 확인
   ↓
🧾 주문 전달 → 🧑‍🍳 사장님 화면에서 확인 · 처리
```

<br/>

## 💻 기술 스택

| 역할 | 종류 | 선정 이유 |
|---|---|---|
| Frontend | ![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=React&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=black) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=Vite&logoColor=white) | 컴포넌트 단위로 화면을 재사용하고, 빠른 개발 서버로 반복 수정에 유리 |
| Routing | ![React Router](https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=ReactRouter&logoColor=white) | 진입 → 메뉴 → 음성 → 확인 → 주문 현황 화면 흐름을 선언적으로 구성 |
| State | ![Zustand](https://img.shields.io/badge/Zustand-443E38?style=for-the-badge&logo=React&logoColor=white) | 세션·소리 설정 등 여러 화면이 함께 쓰는 상태를 가볍게 관리 |
| Data Fetching | ![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=Axios&logoColor=white) | 공통 API 클라이언트로 백엔드 요청·에러 처리를 한곳에서 관리 |
| Voice | Web Speech API | 별도 설치 없이 브라우저 기본 기능으로 음성 인식(STT)·음성 안내(TTS) 구현 |
| Backend | ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=FastAPI&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white) | AI 연동이 쉬운 Python 기반으로 가볍고 빠르게 REST API 구성 |
| Database | ![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=Firebase&logoColor=black) | 별도 DB 서버 없이 매장·장바구니·주문 데이터를 실시간으로 관리 |
| AI | ![Gemini](https://img.shields.io/badge/Gemini-8E75B2?style=for-the-badge&logo=GoogleGemini&logoColor=white) | 자연스러운 말투에서 메뉴·수량·옵션을 추출하는 주문 의도 분석 |
| Formatting | ![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=for-the-badge&logo=ESLint&logoColor=white) ![Prettier](https://img.shields.io/badge/Prettier-000000?style=for-the-badge&logo=Prettier&logoColor=F7B93E) | 코드 스타일을 통일해 협업 시 충돌을 줄임 |
| 협업 | ![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=Notion&logoColor=white) ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=Figma&logoColor=white) | 이슈·PR 관리, API 명세·연동 체크리스트 공유, 화면 설계 |

<br/>

## 👩‍💻 팀원 소개

<!-- TODO: PM·백엔드 팀원 깃허브 아이디와 이름, 담당 확인해서 채우기 -->
| <img src="https://github.com/PM아이디.png" width="100"/> | <img src="https://github.com/omwlsoi.png" width="100"/> | <img src="https://github.com/seokyeonyy.png" width="100"/> | <img src="https://github.com/yedamimi.png" width="100"/> | <img src="https://github.com/BE아이디.png" width="100"/> |
|:---:|:---:|:---:|:---:|:---:|
| [이름](https://github.com/PM아이디) | [이름](https://github.com/omwlsoi) | [석연](https://github.com/seokyeonyy) | [예담](https://github.com/yedamimi) | [지윤](https://github.com/BE아이디) |
| PM | Frontend | Frontend | Backend | Backend |
| 기획 · 디자인 | 초기 세팅 · 진입 · 메뉴 · 확인 · 사장님 페이지 | 음성 주문 페이지 | 담당 | 담당 |

<br/>

## 🚀 실행 방법

> 🔐 키 값은 팀 노션 / DM으로 공유합니다. `.env` 파일은 절대 커밋하지 않아요.

### Backend

```bash
cd backend

# 1. 가상환경 생성 및 활성화
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 2. 패키지 설치
pip install -r requirements.txt

# 3. 환경 변수 설정 (.env)
#    FIREBASE_CREDENTIALS_PATH=  Firebase 서비스 계정 키 파일 경로
#    FIREBASE_DATABASE_URL=      Firebase Realtime Database 주소
#    GEMINI_API_KEY=             Gemini API 키
#    GEMINI_MODEL=               사용할 Gemini 모델명

# 4. 시연용 메뉴 등록 (최초 1회)
python seed_menus.py

# 5. 서버 실행
uvicorn app.main:app --reload
```

### Frontend

```bash
cd frontend

# 1. 패키지 설치
npm install

# 2. 환경 변수 설정
cp .env.example .env.local
#    VITE_API_BASE_URL=/api
#    VITE_API_PROXY_TARGET=http://localhost:8000   (백엔드 주소)

# 3. 실행 → http://localhost:5173
npm run dev
```

> 🎙️ 음성 인식은 Web Speech API를 사용해 <b>Chrome · Edge</b>에서 동작합니다.

<br/>

## 📂 폴더 구조

```
Tello/
├── frontend/
│   ├── public/
│   └── src/
│       ├── api/            # 백엔드 API 호출 (session, order, admin)
│       ├── assets/         # 이미지, 텔로링 캐릭터
│       ├── components/
│       │   ├── common/     # 공통 UI (BigButton, BottomSheet, Header, Toast)
│       │   └── order/      # 주문 UI (MenuCard, CartBar)
│       ├── hooks/          # 음성 인식·음성 안내·대기 타이머 훅
│       ├── mocks/          # 개발용 가상 데이터
│       ├── pages/          # Entry · Menu · Voice · Confirm · OrderStatus · Boss
│       ├── stores/         # Zustand 전역 상태
│       ├── styles/         # 디자인 토큰
│       └── utils/          # formatPrice 등 공통 함수
│
└── backend/
    ├── app/
    │   ├── api/            # 라우터 (sessions, stores, messages, orders, help_requests, admin)
    │   ├── core/           # Firebase 연결, 보안
    │   ├── repositories/   # DB 접근
    │   ├── schemas/        # 요청·응답 모델
    │   ├── services/       # 비즈니스 로직 (LLM 주문 분석, 음성 장바구니, 추천 등)
    │   └── main.py
    ├── seed_menus.py       # 시연용 메뉴 등록
    └── requirements.txt
```

<br/>

## 🌿 협업 규칙

### 브랜치
- `main` : 항상 실행 가능한 상태 유지
- `feature/{domainName}-{detail}` : 기능 개발 (예: `feature/order-voice`)
- `fix/` · `refactor/` : 버그 수정 · 리팩토링

### 커밋 컨벤션
`type: 작업 내용` (예: `feat: 음성 주문 확인 화면 구현`)

| 타입 | 설명 | 타입 | 설명 |
|---|---|---|---|
| `feat` | 새 기능 | `design` | UI/CSS 수정 |
| `fix` | 버그 수정 | `comment` | 주석 추가·변경 |
| `docs` | 문서 수정 | `rename` | 파일·폴더명 변경 |
| `style` | 코드 포맷 | `remove` | 파일 삭제 |
| `refactor` | 리팩토링 | `chore` | 설정·기타 |
| `test` | 테스트 | `!HOTFIX` | 긴급 수정 |

### PR
- 제목: `[타입] #이슈번호 제목`
- 본문: 관련 이슈 · 작업 내용 · 스크린샷 · 리뷰 포인트
- 체크리스트: 커밋 컨벤션 / 로컬 실행 확인 / 불필요한 주석·console.log 제거 / `.env`·키 파일 미포함

### 코드 스타일
- ESLint + Prettier · 세미콜론 · 싱글 쿼트 · 들여쓰기 4칸
- 컴포넌트 `PascalCase` · 함수·변수 `camelCase` · 훅 `usePascalCase`
- Python은 `snake_case`, 클래스는 `PascalCase`
- API 주소는 `/api`로 시작하고, 필드명은 백엔드와 동일하게 사용
- 가격은 서버에서 원 단위 정수로 받고, 화면에서만 `formatPrice`로 변환

<br/>

<div align="center">

<b>Tello</b> — 다름을 바꾸지 않고, 연결합니다.

</div>
