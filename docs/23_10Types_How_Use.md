## 프롬프트 유형과 선택 이유
```
1. [유형 6] 페르소나 기반 응답 생성 (주요 유형)

선택 이유:

가상 문제의 핵심은 '주니어 PM'이 '개발자/디자이너가 이해할 수 있는 기술적 언어'로 문서를 작성하지 못하는 것입니다.

이 문제를 해결하기 위해 AI는 주니어 PM의 부족한 경험을 보완해 줄 수 있는 '숙련된 시니어 PM' 또는 '테크 리드(Tech Lead)'의 페르소나를 부여받아야 합니다.

단순히 아이디어를 나열하는 것이 아니라, AI가 전문가의 입장에서 모호한 아이디어를 DB 설계와 프론트엔드 구조를 잡을 수 있는 수준의 구체적인 명세로 '해석'하고 '재작성'해야 합니다.

2. [유형 8] 지시(Instruction) 및 명령 (보조 유형)

선택 이유:

페르소나를 설정한 후, AI에게 **"추상적인 아이디어를 '웹 프로토타입 제작을 위한 상세 요구사항 리스트'로 변환하라"**는 명확한 '지시'를 내려야 합니다.

또한, "기능적 요구사항", "비기능적 요구사항", "필요한 페이지 구조"라는 구체적인 결과물 형식을 '명령'해야 합니다. 이는 참조 자료의 **[유형 10: 템플릿 (Template)]**의 특성도 일부 포함합니다.
```

## 작성 위해 추가 필요 요건
```
1. 핵심 기능 구체화 (Feature Specifics)

"식단 입력"의 방식: 사용자가 식단을 어떻게 입력합니까?

(예: 음식 이름 텍스트 검색, 사진 촬영 후 자동 인식, 바코드 스캔, 즐겨찾기 목록에서 선택 등)

"칼로리 계산"의 기준: 칼로리 계산은 무엇을 기반으로 합니까?

(예: 자체 구축한 식품 영양 DB 필요 여부, 외부 식품 DB API 연동 여부, 사용자가 직접 칼로리 입력 등)

"깔끔한 대시보드"의 구성 요소: 대시보드에 무엇이 보여야 합니까?

(예: 일일 총 섭취 칼로리, 탄수화물/단백질/지방 비율(매크로), 주간 칼로리 섭취 추이 그래프, 권장 섭취량 대비 달성률 등)

2. 사용자 정의 및 흐름 (User Definition & Flow)

핵심 타겟 사용자: 이 서비스의 주요 사용자는 누구입니까?

(예: 전문 보디빌더, 다이어터, 특정 질환(당뇨 등) 보유자 등. 대상에 따라 필요한 데이터와 기능이 완전히 달라짐)

핵심 사용자 시나리오 (User Scenario): 사용자가 이 서비스를 사용하는 핵심 목적은 무엇입니까?

(예: "체중 감량을 위해 매일 섭취 칼로리를 2000kcal 미만으로 관리한다.")

3. 벤치마킹 및 범위 (Benchmark & Scope)

참고할 만한 레퍼런스: '깔끔하다'고 생각하는 벤치마킹 경쟁 앱/웹이 있습니까?

(예: MyFitnessPal, FatSecret, Noom 등. 구체적인 예시가 있으면 디자인팀의 이해도가 높아짐)

MVP의 명확한 범위: "회원가입", "식단 입력", "리포트 출력" 외에 MVP에 반드시 포함되어야 하거나 제외되어야 할 기능은 무엇입니까?

(예: 소셜 로그인(구글/카카오) 포함 여부, 커뮤니티 기능 제외 여부 등)
```

## 가상 문제 상황
```
1. 가상 문제 상황 (Scenario Challenge)
페르소나 (Persona):
직무: 헬스케어 스타트업 '웰니스 핏(Wellness Fit)'의 주니어 PM (Product Manager)
성향: 아이디어는 많지만, 이를 개발자나 디자이너가 이해할 수 있는 기술적 언어로 정리하는 데 어려움을 겪고 있음.
배경 (Background):
당신은 개인 맞춤형 영양 관리 웹 서비스인 '뉴트리 가이드(Nutri-Guide)'의 MVP(최소 기능 제품) 웹 프로토타입을 기획 중입니다.
일주일 뒤, 개발팀 및 디자인팀과 함께 '프로토타입 제작 킥오프 미팅'이 예정되어 있습니다.
현재는 "사용자가 식단을 입력하면 칼로리를 계산해준다", "깔끔한 대시보드가 있었으면 좋겠다" 정도의 추상적인 아이디어만 나열된 상태입니다.
핵심 문제 (Problem):
개발 리더로부터 **"기능 명세가 너무 모호해서 DB 설계나 프론트엔드 구조를 잡을 수 없다"**는 피드백을 받았습니다.
구체적인 필수 기능 리스트(Feature List), 사용자 흐름(User Flow), 데이터 요구사항이 정의되지 않으면 프로젝트 착수가 무기한 연기될 위기입니다.
해결 과제 (Task):
추상적인 아이디어를 개발자와 디자이너가 즉시 작업할 수 있는 수준의 **'웹 프로토타입 제작을 위한 상세 요구사항 리스트'**로 변환해야 합니다.
기능적 요구사항(회원가입, 식단 입력, 리포트 출력 등)과 비기능적 요구사항(보안, 로딩 속도 등), 그리고 필요한 페이지 구조를 빠짐없이 도출해내야 합니다.

2. 훈련 초점 (Training Focus)
이 문제는 [구조적 분석 및 세분화 (Structural Breakdown)] 능력을 평가.
단순히 "아이디어를 내줘"가 아니라, 모호한 요청을 **체계적인 카테고리(Front-end, Back-end, UX/UI 등)**로 나누어 구체화하는 프롬프팅 스킬이 필요.

```

## 문제 해결 프롬프트
```
# [URGENT] '뉴트리 가이드' MVP 상세 요구사항 리스트 작성 요청

### 1. Persona (AI 역할 설정)

당신은 국내 유수의 **웹 에이전시 'TPA(Tech Partner Alliance)'의 시니어 PM 겸 테크 리드(Tech Lead)**입니다.
당신은 클라이언트(주니어 PM)의 추상적인 아이디어를 실제 개발자가 작업할 수 있는 **구체적인 기능 명세, DB 스키마 제안, API 엔드포인트 정의**로 변환하는 데 특화된 전문가입니다.
당신의 임무는 모호한 기획을 **[UX/UI], [Front-end], [Back-end]**의 체계적인 카테고리로 분류하고 구조화하여 개발팀의 혼란을 막는 것입니다.

---

### 2. Context (현재 배경 및 문제 상황)

* **요청자:** 헬스케어 스타트업 '웰니스 핏'의 주니어 PM입니다.
* **프로젝트:** 개인 맞춤형 영양 관리 웹 서비스 '뉴트리 가이드(Nutri-Guide)' MVP 기획 중입니다.
* **핵심 문제:** 현재 아이디어가 너무 추상적이라, 외주 개발사(당신 회사)의 개발 리더로부터 "이대로는 DB 설계나 프론트엔드 구조를 잡을 수 없다"는 피드백을 받았습니다.
* **긴급 과제:** 일주일 뒤 킥오프 미팅 전까지 개발팀이 즉시 작업에 착수할 수 있는 '상세 요구사항 리스트'가 필요합니다.

---

### 3. Input Data (주니어 PM의 추상적 아이디어 및 가정)

AI(시니어 PM)가 작업을 수행하기 위한 최소한의 입력값입니다.

#### A. 추상적 아이디어
1.  "사용자가 식단을 입력하면 칼로리를 계산해준다."
2.  "깔끔한 대시보드가 있었으면 좋겠다."
3.  "회원가입, 식단 입력, 리포트 출력이 필수 기능이다."

#### B. MVP를 위한 주요 가정 (Key Assumptions)
* **핵심 타겟:** 체중 감량을 목표로 하는 일반 다이어터 (전문 보디빌더 X)
* **식단 입력 방식:** [텍스트 검색]으로 음식 선택 (MVP에서 사진 인식, 바코드 스캔은 제외)
* **영양 정보 DB:** [공공 데이터 포털]의 식품 영양성분 DB API 활용 (자체 DB 구축 X)
* **회원가입:** [소셜 로그인 (구글)]만 우선 지원 (일반 이메일 가입 X)
* **대시보드:** 일일 섭취 칼로리, 탄수화물/단백질/지방(탄단지) 섭취 비율 그래프
* **리포트:** 주간 섭취 칼로리 평균, 체중 변화 추이 (PDF 다운로드 등은 제외)

---

### 4. Task (명령 및 지시)

위 **[Persona]**와 **[Context]**, **[Input Data]**를 기반으로, 개발팀이 즉시 작업할 수 있는 **'뉴트리 가이드 MVP 웹 프로토타입 상세 요구사항 리스트'**를 작성해 주세요.

**[중요]** 모든 산출물은 아래 **[5. Output Template]**에 맞춰 **[구조적 분석 및 세분화]** 원칙에 따라 카테고리별로 명확하게 분류하여 작성해야 합니다.

---

### 5. Output Template (요구하는 산출물 형식)

## 1. UX/UI 기획 (페이지 구조 및 사용자 흐름)

* **A. 필수 페이지 정의 (Page List)**
    * (예: /login - 소셜 로그인 페이지, /dashboard - 메인 대시보드, /record - 식단 기록 페이지...)
* **B. 핵심 사용자 흐름 (Key User Flow)**
    * (예: 1. (로그인) -> 2. (대시보드) -> 3. (식단 기록 버튼 클릭) -> 4. (음식 검색 및 추가) -> 5. (대시보드 반영 확인))

## 2. Front-end 개발 요구사항

* **A. 주요 컴포넌트 (Component List)**
    * (예: `HeaderComponent`, `FoodSearchModal`, `DailyCalorieChart` (D3.js 또는 Chart.js 사용 제안)...)
* **B. 상태 관리 (State Management)**
    * (예: 사용자의 일일 섭취 기록, 로그인 상태(Token) 등 전역 상태 관리 필요...)
* **C. API 연동 목록 (Client-side)**
    * (예: `GET /api/v1/user/me`, `POST /api/v1/record`, `GET /api/v1/foods?query=...`)

## 3. Back-end (서버/DB) 개발 요구사항

* **A. API 엔드포인트 (Endpoint Definition)**
    * (예: `POST /api/v1/auth/google` - 구글 로그인 처리, `GET /api/v1/report?type=weekly` - 주간 리포트 데이터 반환...)
* **B. DB 모델링 (Schema Design)**
    * (예: `Users` (UserID, Email, Name, GoogleID...), `Records` (RecordID, UserID, FoodName, Kcal, Protein...), `Foods` (공공 DB 캐싱용 테이블)...)
* **C. 외부 API 연동 (Server-side)**
    * (예: 식품의약품안전처 공공 API 호출 및 필요 데이터 가공 로직...)

## 4. 비기능적 요구사항 (Non-Functional)

* (예: [보안] JWT 토큰 기반 인증, [성능] 대시보드 로딩 속도 3초 이내 목표...)
```

## 프롬프트 실행 결과
# '뉴트리 가이드' MVP 웹 프로토타입 상세 요구사항 리스트
**Project:** Nutri-Guide (Wellness Fit)
**Author:** TPA (Tech Partner Alliance) - Senior PM/Tech Lead
**Date:** 2025-11-14

## 1. UX/UI 기획 (페이지 구조 및 사용자 흐름)

### A. 필수 페이지 정의 (Page List)

MVP 범위 내에서 총 5개의 핵심 페이지(View)가 필요합니다.

1.  **`/` (루트):**
    * 기능: 인증 상태 확인.
    * 흐름: 비로그인 시 `/login`으로 리디렉션, 로그인 시 `/dashboard`로 리디렉션.
2.  **`/login` (소셜 로그인 페이지):**
    * 기능: '구글 계정으로 시작하기' 버튼 제공. (MVP 범위: 구글 로그인 전용)
3.  **`/dashboard` (메인 대시보드):**
    * 기능: 사용자의 핵심 정보를 시각화.
    * 표시 요소:
        * 오늘 날짜 (Date Picker 포함)
        * 일일 총 섭취 칼로리 vs 목표 칼로리 (예: 도넛 차트)
        * 일일 탄수화물/단백질/지방 섭취 비율 (예: 막대 또는 파이 차트)
        * 끼니별(아침/점심/저녁/간식) 섭취 내역 요약
        * '식단 기록하기' CTA(Call To Action) 버튼
4.  **`/record` (식단 기록 페이지):**
    * 기능: 음식 검색 및 끼니별 기록.
    * 표시 요소:
        * 날짜 선택 (기본값: 오늘)
        * 끼니 선택 탭 (아침/점심/저녁/간식)
        * 음식 검색창 (텍스트 기반)
        * 검색 결과 리스트 (공공 DB API 연동)
        * 선택한 음식 목록 및 '기록 완료' 버튼
5.  **`/report` (주간 리포트 페이지):**
    * 기능: 주간 데이터 요약.
    * 표시 요소:
        * 주간 칼로리 섭취 추이 (예: 라인 차트)
        * 주간 체중 변화 추이 (예: 라인 차트) (단, 체중 입력은 `/settings` 또는 모달로 처리)
6.  **(추가 제안) `/settings` (설정 페이지):**
    * 기능: 리포트 및 칼로리 계산의 기준이 되는 사용자 정보 입력.
    * 표시 요소:
        * 현재 체중, 목표 체중
        * 일일 목표 섭취 칼로리 (수동 입력)
        * 로그아웃 버튼

### B. 핵심 사용자 흐름 (Key User Flow)

**[Flow 1: 신규 사용자 가입 및 설정]**
1.  사용자가 `/login` 페이지 접근.
2.  '구글 계정으로 시작하기' 클릭.
3.  구글 인증 완료 후, 신규 사용자인 경우 `/settings`로 강제 이동.
4.  사용자가 '목표 칼로리'(예: 2000kcal)와 '현재 체중' 입력 후 저장.
5.  `/dashboard`로 이동.

**[Flow 2: 기존 사용자 식단 기록]**
1.  사용자가 `/dashboard` 접근.
2.  '식단 기록하기' 버튼 클릭 -> `/record` 페이지로 이동.
3.  '점심' 탭 선택.
4.  검색창에 "닭가슴살" 입력.
5.  검색 결과에서 "닭가슴살 샐러드 (150kcal)" 선택 및 '추가' 클릭.
6.  '기록 완료' 버튼 클릭.
7.  `/dashboard`로 자동 이동하며, '일일 총 섭취 칼로리' 및 '탄단지 비율' 차트가 즉시 업데이트됨.

## 2. Front-end 개발 요구사항

* **기술 스택 제안:** React (Next.js) 또는 Vue.js (Nuxt.js) / 상태 관리: React Query (or SWR) / 차트: Chart.js

### A. 주요 컴포넌트 (Component List)

* `Layout/Header`: 로고, '대시보드', '리포트' 네비게이션, '설정' 아이콘
* `Auth/GoogleLoginButton`: 구글 로그인 SDK 연동 버튼
* `Common/DateNavigator`: 날짜(일)를 변경하는 좌우 화살표 버튼
* `Dashboard/DailyCalorieChart`: 일일 칼로리 도넛 차트 (Props: `currentKcal`, `targetKcal`)
* `Dashboard/MacroRatioChart`: 탄단지 비율 차트 (Props: `protein`, `carb`, `fat`)
* `Dashboard/MealSummaryCard`: 끼니별(아침/점심...) 요약 카드
* `Record/FoodSearchBar`: '공공 DB' 연동 검색창 (입력 시 딜레이(debounce) 적용 필수)
* `Record/FoodSearchResultList`: 검색된 음식 목록 (항목 클릭 시 '추가' 이벤트 발생)
* `Report/WeeklyTrendChart`: 주간 데이터 라인 차트 (Props: `data`, `labels`)
* `Settings/ProfileForm`: 사용자 목표 칼로리, 체중 입력 폼

### B. 상태 관리 (State Management)

* `useAuthStore` (전역): 사용자의 로그인 상태(JWT 토큰), 이메일, 이름 관리.
* `useQuery('/api/v1/dashboard?date=...')`: (React Query) 선택된 날짜(`date`)에 해당하는 대시보드 데이터를 서버로부터 받아와 캐싱.
* `useQuery('/api/v1/report?type=weekly&...')`: 주간 리포트 데이터 캐싱.
* `useMutation('/api/v1/records')`: 식단 기록 추가/삭제 시 서버에 POST/DELETE 요청 및 관련 `dashboard` 쿼리 자동 갱신(invalidate).

### C. API 연동 목록 (Client-side)

* `POST /api/v1/auth/google` (Body: { googleToken })
* `GET /api/v1/user/profile` (Auth Header 필요)
* `PUT /api/v1/user/profile` (Auth Header 필요)
* `GET /api/v1/dashboard?date=YYYY-MM-DD` (Auth Header 필요)
* `GET /api/v1/foods?query=[검색어]` (Auth Header 필요)
* `POST /api/v1/records` (Auth Header 필요, Body: { ... })
* `GET /api/v1/reports/weekly?endDate=YYYY-MM-DD` (Auth Header 필요)

## 3. Back-end (서버/DB) 개발 요구사항

* **기술 스택 제안:** Node.js (Express 또는 NestJS) / DB: PostgreSQL (또는 MySQL) / 인증: JWT

### A. API 엔드포인트 (Endpoint Definition)

* **Auth (인증)**
    * `POST /api/v1/auth/google`: 구글 토큰 검증. `Users` DB 조회/생성 후, 서비스 자체 JWT 발급.
* **User (사용자)**
    * `GET /api/v1/user/profile`: (인증 필요) 현재 로그인된 사용자 정보(`targetKcal`, `weight`) 반환.
    * `PUT /api/v1/user/profile`: (인증 필요) 사용자 정보 업데이트.
* **Record (기록)**
    * `POST /api/v1/records`: (인증 필요) 식단 기록 생성 (Body: `foodName`, `kcal`, `protein`, `carb`, `fat`, `mealType`, `consumedAt`)
    * `DELETE /api/v1/records/:recordId`: (인증 필요) 본인 기록 삭제.
* **Dashboard (대시보드)**
    * `GET /api/v1/dashboard`: (인증 필요) 쿼리 스트링(`?date=...`) 기준, 해당 날짜의 Kcal, 탄단지 총합 집계 데이터 반환.
* **Report (리포트)**
    * `GET /api/v1/reports/weekly`: (인증 필요) 쿼리 스트링(`?endDate=...`) 기준, 7일간의 Kcal 섭취 추이 및 체중 변화 추이 반환.
* **Food (음식 정보)**
    * `GET /api/v1/foods`: (인증 필요) 쿼리 스트링(`?query=...`)으로 공공 DB API 호출 및 결과 반환.

### B. DB 모델링 (Schema Design)

1.  **Users** (사용자)
    * `userId` (PK, UUID): 사용자 고유 ID
    * `googleId` (String, Unique): 구글 소셜 ID
    * `email` (String, Unique): 이메일
    * `name` (String): 이름
    * `targetKcal` (Int, Default: 2000): 목표 칼로리
    * `createdAt` (DateTime)

2.  **Records** (식단 기록)
    * `recordId` (PK, UUID): 기록 고유 ID
    * `userId` (FK, `Users` 테이블 참조): 사용자 ID
    * `foodName` (String): 음식 이름 (검색된 이름)
    * `kcal` (Int): 칼로리
    * `protein` (Float): 단백질(g)
    * `carb` (Float): 탄수화물(g)
    * `fat` (Float): 지방(g)
    * `mealType` (Enum: 'breakfast', 'lunch', 'dinner', 'snack'): 끼니 구분
    * `consumedAt` (Date): 섭취 날짜 (시간 제외 날짜만)

3.  **WeightLogs** (체중 기록)
    * `logId` (PK, UUID): 로그 ID
    * `userId` (FK, `Users` 테이블 참조): 사용자 ID
    * `weight` (Float): 체중(kg)
    * `loggedAt` (Date): 기록 날짜

### C. 외부 API 연동 (Server-side)

* **[필수] 식품의약품안전처 - 식품영양성분 DB API:**
    * `GET /api/v1/foods` 요청 시, 서버가 이 API를 호출하여 음식명 검색 및 영양 정보(Kcal, 탄단지)를 받아와야 함.
* **[권장] 공공 API 결과 캐싱:**
    * 자주 검색되는 음식(예: "밥", "닭가슴살")은 우리 `Foods` 캐시 테이블에 저장하여, 공공 API 호출 횟수를 줄이고 응답 속도를 향상시킴.

## 4. 비기능적 요구사항 (Non-Functional)

* **보안:**
    * 모든 API는 HTTPS(SSL)를 통해 서비스되어야 합니다.
    * 모든 사용자 인증은 JWT(Access Token) 기반으로 처리하며, 클라이언트는 토큰을 안전하게 저장(예: HttpOnly Cookie 또는 Secure Storage)해야 합니다.
* **성능:**
    * 대시보드 로딩(데이터 포함)은 3초 이내를 목표로 합니다.
    * 음식 검색(공공 API 연동) 응답 속도는 1.5초 이내를 목표로 합니다. (서버 사이드 캐시 적용 권장)
* **플랫폼 호환성:**
    * 웹 (PC, 모바일) 반응형 디자인을 준수합니다. (Chrome, Safari 최신 버전 호환)