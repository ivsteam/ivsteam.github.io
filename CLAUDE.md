# 인베슘 (Invesume) 프로젝트 - Claude AI 가이드

## 📋 프로젝트 개요

**인베슘 (Invesume)**은 12년 이상의 경험을 가진 오픈소스 전문 기업으로, Sovereign AI 플랫폼과 한국형 리눅스 OS를 개발합니다.

- **웹사이트**: https://invesume.com
- **제품**: AI.RUN/Hamonize (Sovereign AI), HamoniKR OS (리눅스 배포판), 오픈소스 컨설팅
- **목표**: 오픈소스 생태계 확산 및 Sovereign AI 기술 보급
- **대상 고객**: 정부 기관, 공공 기관, 기업

---

## 🎨 필수: 디자인 시스템 사용

### ⚠️ 중요 지침

**모든 UI/디자인 관련 작업에서는 반드시 인베슘 디자인 시스템을 사용해야 합니다.**

### 디자인 시스템 파일 위치

```
static/design-system.html     # ⭐ 시각적 스타일 가이드 (브라우저에서 확인)
static/design-system.css      # 디자인 토큰 및 컴포넌트 스타일
DESIGN_SYSTEM_GUIDE.md        # 상세 사용 가이드
DESIGN_TOKENS.md              # 빠른 참조 레퍼런스
```

**스타일 가이드 접속 URL**: `http://localhost:1313/design-system.html`

### 디자인 토큰 사용법

**✅ 항상 CSS 변수(디자인 토큰)을 사용하세요:**

```css
/* 올바른 예 */
.button-primary {
    background-color: var(--color-primary-500);
    color: var(--text-inverse);
    padding: var(--spacing-3) var(--spacing-6);
    border-radius: var(--radius-base);
    font-size: var(--font-size-base);
    font-weight: var(--font-weight-semibold);
}

.card {
    background: var(--bg-primary);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-sm);
    padding: var(--spacing-6);
}

.section-title {
    font-size: var(--font-size-2xl);
    font-weight: var(--font-weight-bold);
    color: var(--color-primary-800);
    margin-bottom: var(--spacing-6);
}
```

**❌ 절대 하드코딩된 값을 사용하지 마세요:**

```css
/* 잘못된 예 */
.button-primary {
    background-color: #1a8f7a;  /* ❌ 하드코딩된 색상 */
    color: #ffffff;            /* ❌ 하드코딩된 색상 */
    padding: 12px 24px;        /* ❌ 매직 넘버 */
    border-radius: 8px;        /* ❌ 매직 넘버 */
    font-size: 16px;           /* ❌ 매직 넘버 */
}
```

### 주요 디자인 토큰

#### 색상 (Colors)
```css
/* Primary - 브랜드 색상 */
--color-primary-500: #1a8f7a  /* 메인 액센트 */
--color-primary-800: #081f19  /* 다크 그린 */

/* Semantic - 의미 있는 색상 */
--color-success: #0d8a61      /* 성공 */
--color-warning: #f59e0b      /* 경고 */
--color-danger: #ef4444       /* 오류 */
--color-info: #3b82f6         /* 정보 */

/* Text & Background */
--text-primary: #111827        /* 주요 텍스트 */
--text-secondary: #4a5568      /* 보조 텍스트 */
--bg-primary: #ffffff         /* 주요 배경 */
--bg-secondary: #f8fafc       /* 보조 배경 */
```

#### 타이포그래피 (Typography)
```css
--font-size-base: 1rem        /* 16px - 기본 */
--font-size-lg: 1.125rem      /* 18px */
--font-size-xl: 1.25rem       /* 20px */
--font-size-2xl: 1.5rem       /* 24px */
--font-size-3xl: 1.875rem     /* 30px */

--font-weight-semibold: 600   /* 제목, 강조 */
--font-weight-bold: 700       /* 메인 제목 */
```

#### 간격 (Spacing)
```css
--spacing-2: 0.5rem   /* 8px - 작은 간격 */
--spacing-4: 1rem     /* 16px - 기본 간격 */
--spacing-6: 1.5rem   /* 24px - 중간 간격 */
--spacing-8: 2rem     /* 32px - 큰 간격 */
--spacing-12: 3rem    /* 48px - 섹션 간격 */
```

---

## 🧩 기존 컴포넌트 사용

### 1. 버튼 (Buttons)

```html
<!-- Primary 버튼 -->
<button class="btn btn-primary">제출</button>

<!-- Secondary 버튼 -->
<button class="btn btn-secondary">취소</button>

<!-- Outline 버튼 -->
<button class="btn btn-outline">자세히 보기</button>

<!-- Ghost 버튼 -->
<button class="btn btn-ghost">닫기</button>

<!-- 버튼 크기 -->
<button class="btn btn-primary btn-sm">작은 버튼</button>
<button class="btn btn-primary">기본 버튼</button>
<button class="btn btn-primary btn-lg">큰 버튼</button>
```

### 2. 카드 (Cards)

```html
<div class="card">
    <img src="image.jpg" alt="제품" class="card-image">
    <div class="card-body">
        <h4 class="card-title">카드 제목</h4>
        <p class="card-text">카드 내용입니다.</p>
    </div>
    <div class="card-footer">
        <button class="btn btn-primary btn-sm">버튼</button>
    </div>
</div>
```

### 3. 폼 (Forms)

```html
<!-- 입력 필드 -->
<div class="form-group">
    <label class="form-label">이메일</label>
    <input type="email" class="form-input" placeholder="example@invesume.com">
    <span class="form-help">도움말 텍스트</span>
</div>

<!-- 드롭다운 -->
<div class="form-group">
    <label class="form-label">옵션 선택</label>
    <select class="form-select">
        <option>옵션 1</option>
        <option>옵션 2</option>
    </select>
</div>

<!-- 텍스트 영역 -->
<div class="form-group">
    <label class="form-label">메시지</label>
    <textarea class="form-textarea" placeholder="메시지 입력"></textarea>
</div>
```

### 4. 배지 (Badges)

```html
<span class="badge badge-primary">Primary</span>
<span class="badge badge-success">Success</span>
<span class="badge badge-warning">Warning</span>
<span class="badge badge-danger">Danger</span>
<span class="badge badge-outline">Outline</span>
```

### 5. 알림 (Alerts)

```html
<div class="alert alert-success">
    <div class="alert-title">성공!</div>
    <p>작업이 완료되었습니다.</p>
</div>

<div class="alert alert-danger">
    <div class="alert-title">오류!</div>
    <p>문제가 발생했습니다.</p>
</div>
```

---

## 🏗️ 레이아웃 구조

### HTML 템플릿 위치

```
layouts/
├── _default/
│   ├── baseof.html           # 기본 레이아웃
│   ├── single.html           # 단일 페이지
│   └── list.html            # 리스트 페이지
├── index.html               # 메인 페이지
├── products/
│   ├── list.html            # 제품 리스트
│   └── single.html          # 제품 상세
└── partials/
    ├── header.html          # 헤더
    └── footer.html          # 푸터
```

### CSS 파일 위치

```
static/css/
└── custom.css              # 커스텀 스타일
```

---

## 🎯 디자인 원칙

### 1. 색상 사용

- **Primary 색상** (`--color-primary-500`): 주요 버튼, 링크, 강조 요소
- **Dark Green** (`--color-primary-800`): 헤더, 푸터, 다크 섹션
- **Secondary Gray** (`--color-gray-600`): 보조 텍스트
- **배경색** (`--bg-primary`, `--bg-secondary`): 페이지 및 카드 배경

### 2. 간격 사용

- **요소 내부**: `--spacing-4` (16px)
- **관련 요소 간**: `--spacing-6` (24px)
- **섹션 간**: `--spacing-12` (48px)
- **아이콘과 텍스트 사이**: `--spacing-2` (8px)

### 3. 타이포그래피

- **메인 제목**: `--font-size-3xl` (30px)
- **섹션 제목**: `--font-size-2xl` (24px)
- **본문**: `--font-size-base` (16px)
- **작은 텍스트**: `--font-size-sm` (14px)

---

## 📝 코드 작성 표준

### CSS 작성 시

1. **항상 디자인 토큰 사용**: `var(--color-primary-500)`
2. **BEM 네이밍 권장**: `.block__element--modifier`
3. **반응형 고려**: Mobile First 접근
4. **접근성 준수**: 충분한 색상 대비, 포커스 상태

### HTML 작성 시

1. **시맨틱 태그 사용**: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`
2. **의미 있는 클래스명**: `.product-card`, `.hero-section`
3. **알트 텍스트 포함**: 모든 이미지에 `alt` 속성
4. **폼 라벨 필수**: 모든 입력 필드에 `<label>`

### JavaScript 작성 시

1. **필요한 경우에만 사용**: 순수 CSS로 해결 가능하면 CSS 우선
2. **접근성 고려**: 키보드 내비게이션 지원
3. **성능 최적화**: 불필요한 DOM 조작 피하기

---

## 🚀 새로운 페이지/기능 추가 시

### 1. 디자인 시스템 확인

```bash
# 1. design-system.html 열어서 참조
# 브라우저에서 http://localhost:1313/design-system.html 열기

# 2. DESIGN_TOKENS.md 빠른 참조
# 필요한 토큰 찾기

# 3. DESIGN_SYSTEM_GUIDE.md 예제 확인
# 비슷한 컴포넌트 예제 찾기
```

### 2. 새로운 컴포넌트 만들 때

```css
/* 디자인 토큰 사용하여 스타일 정의 */
.new-component {
    padding: var(--spacing-6);
    background: var(--bg-primary);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-sm);
}

.new-component__title {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-semibold);
    color: var(--color-primary-800);
    margin-bottom: var(--spacing-4);
}

.new-component--highlight {
    border: 2px solid var(--color-primary-500);
}
```

### 3. 기존 스타일 수정 시

- **디자인 토큰 값 수정 ❌**: `design-system.css`의 `:root` 변수 직접 수정 금지
- **새로운 컴포넌트 추가 ✅**: 필요하다면 새로운 클래스 추가
- **오버라이드 최소화 ✅**: 기존 컴포넌트 스타일 오버라이드 피하기

---

## 🌐 다국어 지원

### 언어 설정

- **기본 언어**: 한국어 (`ko`)
- **지원 언어**: 한국어, 영어 (`en`)
- **언어 전환**: 헤더의 KO | EN 링크

### 다국어 컨텐츠

```
content/
├── _index.md           # 한국어 메인
├── about.md            # 한국어 회사소개
└── en/
    ├── _index.md       # 영어 메인
    └── about.md        # 영어 회사소개
```

---

## 🎨 시각적 자산

### SVG 아이콘 및 일러스트

```
static/img/
├── hero-bg.svg                # 히어로 배경
├── features/
│   ├── feature-ai.svg        # AI 아이콘
│   ├── feature-code.svg      # 코드 아이콘
│   ├── feature-innovation.svg # 혁신 아이콘
│   └── feature-trust.svg     # 신뢰 아이콘
├── products/                 # 제품 헤더
├── sections/                 # 섹션 배경
├── patterns/                 # 배경 패턴
└── dividers/                 # 섹션 구분선
```

### 이미지 사용 가이드

- **제품 이미지**: `/img/products/`
- **이벤트 이미지**: `/img/events/`
- **고객사 로고**: `/img/customers/`
- **인증서**: `/img/credentials/`

---

## 🔧 개발 도구

### Hugo 서버

```bash
# 로컬 개발 서버 시작
hugo server

# 초안 보기 (draft 포함)
hugo server -D

# 특정 포트
hugo server --port 1313
```

### 빌드

```bash
# 프로덕션 빌드
hugo

# 스테이징 빌드
hugo --environment staging
```

---

## ✅ 품질 체크리스트

### 배포 전 확인

- [ ] 디자인 토큰이 올바르게 사용되었는가?
- [ ] 모든 링크가 작동하는가?
- [ ] 모든 이미지에 alt 텍스트가 있는가?
- [ ] 폼 요소에 라벨이 있는가?
- [ ] 반응형 디자인이 모바일에서 작동하는가?
- [ ] 브라우저 호환성 (Chrome, Firefox, Safari, Edge)
- [ ] 다국어 링크가 올바른가?
- [ ] 접근성 (키보드 내비게이션, 색상 대비)

---

## 🚫 금지 사항

### 절대 하지 마세요

1. **하드코딩된 색상 사용**: `#1a8f7a` 대신 `var(--color-primary-500)`
2. **매직 넘버 사용**: `16px` 대신 `var(--spacing-4)`
3. **인라인 스타일**: `<div style="color: red;">` 금지
4. `!important` 사용: 최후의 수단으로만 사용
5. **Font Awesome 직접 사용**: 디자인 시스템의 SVG 아이콘 사용 우선
6. **Bootstrap 클래스만 사용**: 디자인 시스템 컴포넌트 사용 우선

---

## 📚 추가 참고 자료

### 내부 문서
- `README.md`: 프로젝트 개요
- `DESIGN_SYSTEM_GUIDE.md`: 디자인 시스템 상세 가이드
- `DESIGN_TOKENS.md`: 디자인 토큰 레퍼런스
- `UI_IMPROVEMENTS.md`: UI 개선 내역
- `HTML_INTEGRATION_EXAMPLES.md`: HTML 통합 예제

### 외부 참고
- Hugo 문서: https://gohugo.io/documentation/
- Bootstrap 문서: https://getbootstrap.com/docs/5.3/

---

## 💬 사용자 피드백

사용자가 디자인 시스템 사용을 요청하거나, 새로운 UI를 만들 때:

1. **먼저 디자인 시스템 확인**: `design-system.html` 참조
2. **기존 컴포넌트 재사용**: 가능하면 기존 컴포넌트 활용
3. **디자인 토큰 사용**: 항상 CSS 변수 사용
4. **일관성 유지**: 전체 사이트와 일관된 디자인

---

**버전**: 1.0.0
**마지막 업데이트**: 2026-04-11
**유지관리자**: Invesume Development Team

이 문서는 인베슘 프로젝트에서 Claude AI가 일관되고 품질 높은 코드를 작성하도록 돕기 위한 가이드입니다.
