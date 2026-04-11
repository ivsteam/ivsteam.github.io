# 인베슘 디자인 시스템 사용 가이드

## 📋 목차

1. [디자인 토큰 개요](#디자인-토큰-개요)
2. [색상 사용법](#색상-사용법)
3. [타이포그래피](#타이포그래피)
4. [간격 스페이싱](#간격-스페이싱)
5. [컴포넌트 사용법](#컴포넌트-사용법)
6. [실전 예제](#실전-예제)
7. [베스트 프랙티스](#베스트-프랙티스)

---

## 디자인 토큰 개요

디자인 토큰은 디자인 시스템의 기본 building block입니다. CSS 변수로 정의되어 있으며, 일관된 디자인을 유지하면서 쉽게 커스터마이징할 수 있습니다.

### 파일 구조

```
static/
├── design-system.css    # 디자인 토큰 및 스타일 정의
design-system.html       # 스타일 가이드 페이지
```

### 디자인 토큰 카테고리

1. **Color Tokens** - 색상 팔레트
2. **Typography Tokens** - 폰트 크기, 웨이트, 라인 높이
3. **Spacing Tokens** - 간격 시스템
4. **Border Radius** - 테두리 라운드
5. **Shadows** - 그림자 효과
6. **Transitions** - 애니메이션 속도

---

## 색상 사용법

### Primary Colors

```css
/* 주요 색상 - 브랜드 아이덴티티 */
--color-primary-500: #1a8f7a;  /* 메인 액센트 */
--color-primary-800: #081f19;  /* 다크 그린 */
--color-primary-900: #002821;  /* 짙은 틸 */
```

**사용 예시:**
```css
.button-primary {
    background-color: var(--color-primary-500);
    color: white;
}

.header {
    background-color: var(--color-primary-800);
}
```

### Semantic Colors

```css
/* 의미 있는 색상 */
--color-success: #0d8a61;   /* 성공 */
--color-warning: #f59e0b;   /* 경고 */
--color-danger: #ef4444;    /* 오류 */
--color-info: #3b82f6;      /* 정보 */
```

**사용 예시:**
```html
<div class="alert alert-success">
    성공 메시지
</div>

<div class="alert alert-danger">
    오류 메시지
</div>
```

### Neutral Colors

```css
/* 중립 색상 - 텍스트, 배경, 테두리 */
--color-gray-50: #f8fafc;    /* 배경 */
--color-gray-100: #f1f5f9;   /* 배경 */
--color-gray-200: #e2e8f0;   /* 테두리 */
--color-gray-400: #94a3b8;   /* 비활성 */
--color-gray-600: #475569;   /* 보조 텍스트 */
```

### 색상 사용 가이드라인

✅ **권장:**
- 버튼, 링크: `var(--color-primary-500)`
- 헤더, 푸터: `var(--color-primary-800)`
- 페이지 배경: `var(--color-gray-50)`
- 카드 배경: `var(--bg-primary)`

❌ **비권장:**
- 하드코딩된 색상 값 사용
- 너무 밝은 색상의 텍스트
- 충분한 대비가 없는 조합

---

## 타이포그래피

### Font Family

```css
--font-family-base: 'Noto Sans KR', sans-serif;
--font-family-heading: 'Noto Sans KR', sans-serif;
--font-family-mono: 'SF Mono', monospace;
```

### Font Sizes

```css
--font-size-xs: 0.75rem;     /* 12px - 작은 텍스트 */
--font-size-sm: 0.875rem;    /* 14px - 보조 텍스트 */
--font-size-base: 1rem;      /* 16px - 본문 */
--font-size-lg: 1.125rem;    /* 18px - 큰 텍스트 */
--font-size-xl: 1.25rem;     /* 20px - 소제목 */
--font-size-2xl: 1.5rem;     /* 24px - 제목 */
--font-size-3xl: 1.875rem;   /* 30px - 큰 제목 */
--font-size-4xl: 2.25rem;    /* 36px - 헤드라인 */
--font-size-5xl: 3rem;       /* 48px - 히어로 */
```

**사용 예시:**
```css
.hero-title {
    font-size: var(--font-size-5xl);
    font-weight: var(--font-weight-bold);
}

.section-title {
    font-size: var(--font-size-2xl);
    font-weight: var(--font-weight-semibold);
}

.body-text {
    font-size: var(--font-size-base);
    line-height: var(--line-height-normal);
}
```

### Font Weights

```css
--font-weight-light: 300
--font-weight-normal: 400
--font-weight-medium: 500
--font-weight-semibold: 600
--font-weight-bold: 700
```

### Line Heights

```css
--line-height-tight: 1.25     /* 제목 */
--line-height-normal: 1.5     /* 본문 */
--line-height-relaxed: 1.75   /* 긴 텍스트 */
```

---

## 간격 (Spacing)

### Spacing Scale

```css
--spacing-1: 0.25rem;    /* 4px */
--spacing-2: 0.5rem;     /* 8px */
--spacing-3: 0.75rem;    /* 12px */
--spacing-4: 1rem;       /* 16px - 기본 간격 */
--spacing-6: 1.5rem;     /* 24px */
--spacing-8: 2rem;       /* 32px */
--spacing-12: 3rem;      /* 48px */
--spacing-16: 4rem;      /* 64px */
```

**사용 가이드:**

| 용도 | 추천 토큰 | 크기 |
|------|-----------|------|
| 아이콘과 텍스트 사이 | `--spacing-2` | 8px |
| 관련 요소 간 | `--spacing-4` | 16px |
| 섹션 내 그룹 간 | `--spacing-6` | 24px |
| 섹션 간 | `--spacing-12` | 48px |

**실전 예시:**
```css
.card {
    padding: var(--spacing-6);     /* 내부 간격 */
    margin-bottom: var(--spacing-4); /* 외부 간격 */
}

.button {
    padding: var(--spacing-3) var(--spacing-6);
    gap: var(--spacing-2);  /* 아이콘과 텍스트 사이 */
}
```

---

## 컴포넌트 사용법

### 1. 버튼 (Buttons)

#### Primary Button
```html
<button class="btn btn-primary">기본 버튼</button>
```

#### Button Sizes
```html
<button class="btn btn-primary btn-sm">작은 버튼</button>
<button class="btn btn-primary">기본 버튼</button>
<button class="btn btn-primary btn-lg">큰 버튼</button>
```

#### Button Variants
```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-outline">Outline</button>
<button class="btn btn-ghost">Ghost</button>
```

#### Disabled State
```html
<button class="btn btn-primary" disabled>비활성 버튼</button>
```

### 2. 카드 (Cards)

```html
<div class="card">
    <img src="image.jpg" alt="카드 이미지" class="card-image">
    <div class="card-body">
        <h4 class="card-title">카드 제목</h4>
        <p class="card-text">카드 내용입니다.</p>
    </div>
    <div class="card-footer">
        <button class="btn btn-primary btn-sm">버튼</button>
    </div>
</div>
```

### 3. 폼 요소 (Form Elements)

#### Input Field
```html
<div class="form-group">
    <label class="form-label">이메일</label>
    <input type="email" class="form-input" placeholder="example@invesume.com">
    <span class="form-help">도움말 텍스트</span>
</div>
```

#### Select Dropdown
```html
<div class="form-group">
    <label class="form-label">옵션 선택</label>
    <select class="form-select">
        <option>옵션 1</option>
        <option>옵션 2</option>
    </select>
</div>
```

#### Textarea
```html
<div class="form-group">
    <label class="form-label">메시지</label>
    <textarea class="form-textarea" placeholder="메시지를 입력하세요"></textarea>
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

## 실전 예제

### 예제 1: 제품 카드

```html
<div class="card">
    <img src="/img/products/product-1-resized.jpg"
         alt="AI Platform"
         class="card-image">
    <div class="card-body">
        <span class="badge badge-primary mb-4">AI Platform</span>
        <h4 class="card-title">AI.RUN / Hamonize</h4>
        <p class="card-text">
            Sovereign AI Platform - 데이터 프라이버시 기반 AI 플랫폼
        </p>
    </div>
    <div class="card-footer">
        <button class="btn btn-primary btn-sm">자세히 보기</button>
        <button class="btn btn-outline btn-sm">문의하기</button>
    </div>
</div>
```

### 예제 2: 연락처 폼

```html
<form>
    <div class="form-row">
        <div class="form-group">
            <label class="form-label">이름</label>
            <input type="text" class="form-input" placeholder="홍길동">
        </div>
        <div class="form-group">
            <label class="form-label">이메일</label>
            <input type="email" class="form-input" placeholder="example@invesume.com">
        </div>
    </div>

    <div class="form-group">
        <label class="form-label">제목</label>
        <select class="form-select">
            <option>제품 문의</option>
            <option>기술 지원</option>
            <option>파트너십</option>
        </select>
    </div>

    <div class="form-group">
        <label class="form-label">메시지</label>
        <textarea class="form-textarea" placeholder="문의 내용을 입력하세요"></textarea>
    </div>

    <div class="form-group">
        <button type="submit" class="btn btn-primary">보내기</button>
        <button type="reset" class="btn btn-outline">초기화</button>
    </div>
</form>
```

### 예제 3: 통계 카드

```html
<div class="card" style="text-align: center;">
    <div class="card-body">
        <div style="font-size: var(--font-size-5xl); font-weight: var(--font-weight-bold); color: var(--color-primary-500);">
            12년+
        </div>
        <p style="color: var(--text-secondary); margin-top: var(--spacing-2);">
            오픈소스 리더십
        </p>
    </div>
</div>
```

### 예제 4: 히어로 섹션

```html
<section style="background: var(--color-primary-800); color: white; padding: var(--spacing-16) 0;">
    <div style="max-width: 1200px; margin: 0 auto; padding: 0 var(--spacing-8);">
        <h1 style="font-size: var(--font-size-5xl); color: white; margin-bottom: var(--spacing-4);">
            코드를 열어 AI 시대를 여는 기업
        </h1>
        <p style="font-size: var(--font-size-xl); color: rgba(255,255,255,0.9); margin-bottom: var(--spacing-8);">
            12년의 오픈소스 리더십, 이제 Sovereign AI로
        </p>
        <div>
            <button class="btn btn-primary btn-lg">제품 & 서비스</button>
            <button class="btn btn-outline btn-lg">문의하기</button>
        </div>
    </div>
</section>
```

---

## 베스트 프랙티스

### 1. 색상 사용

✅ **DO:**
```css
.button {
    background-color: var(--color-primary-500);
    color: white;
}
```

❌ **DON'T:**
```css
.button {
    background-color: #1a8f7a;  /* 하드코딩하지 마세요 */
    color: #ffffff;
}
```

### 2. 간격 사용

✅ **DO:**
```css
.section {
    padding: var(--spacing-8) var(--spacing-6);
    margin-bottom: var(--spacing-12);
}
```

❌ **DON'T:**
```css
.section {
    padding: 32px 24px;  /* 매직 넘버 피하세요 */
    margin-bottom: 48px;
}
```

### 3. 폰트 사이즈

✅ **DO:**
```css
.title {
    font-size: var(--font-size-2xl);
    font-weight: var(--font-weight-semibold);
}
```

❌ **DON'T:**
```css
.title {
    font-size: 24px;  /* 직접 값 피하세요 */
    font-weight: 600;
}
```

### 4. 반응형 디자인

```css
/* Mobile First */
.container {
    padding: var(--spacing-4);
}

@media (min-width: 768px) {
    .container {
        padding: var(--spacing-8);
    }
}

@media (min-width: 1024px) {
    .container {
        padding: var(--spacing-12);
    }
}
```

### 5. 접근성

```css
/* 충분한 색상 대비 */
.button {
    background-color: var(--color-primary-500);
    color: white;  /* 충분한 대비 */
}

/* 포커스 상태 */
.button:focus {
    outline: 2px solid var(--color-primary-400);
    outline-offset: 2px;
}
```

---

## 커스터마이징

### 테마 색상 변경

```css
:root {
    /* Primary 색상 변경 */
    --color-primary-500: #0d8a61;  /* 다른 녹색 */
    --color-primary-600: #0a6b4d;
    --color-primary-800: #07563f;
}
```

### 폰트 변경

```css
:root {
    --font-family-base: 'Pretendard', sans-serif;
    --font-family-heading: 'Pretendard', sans-serif;
}
```

### 간격 조정

```css
:root {
    /* 더 좁은 간격 */
    --spacing-4: 0.8rem;  /* 기본 1rem */
}
```

---

## 브라우저 지원

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- 모바일 브라우저

---

## 도구 모음

### CSS 변수 추출

```javascript
// 모든 디자인 토큰 값 가져오기
const rootStyles = getComputedStyle(document.documentElement);
const primaryColor = rootStyles.getPropertyValue('--color-primary-500');
console.log(primaryColor); // #1a8f7a
```

### 테마 전환

```javascript
// 다크 모드 전환
document.documentElement.style.setProperty('--bg-primary', '#1a1a1a');
document.documentElement.style.setProperty('--text-primary', '#ffffff');
```

---

## 업데이트 로그

### v1.0.0 (2026-04-11)
- 초기 디자인 시스템 릴리스
- 10개 카테고리의 디자인 토큰
- 기본 컴포넌트 라이브러리
- 스타일 가이드 페이지

---

## 지원 및 문서

- **스타일 가이드**: `design-system.html` (브라우저에서 열어보세요)
- **CSS 파일**: `static/design-system.css`
- **이 가이드**: `DESIGN_SYSTEM_GUIDE.md`

---

**버전**: 1.0.0
**마지막 업데이트**: 2026-04-11
**유지관리자**: Invesume Design Team
