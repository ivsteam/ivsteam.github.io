# 인베슘 디자인 토큰 레퍼런스

## 🎨 빠른 참조 가이드

이 문서는 모든 디자인 토큰을 빠르게 찾을 수 있는 레퍼런스입니다.

---

## 🎯 Color Tokens

### Primary Colors
```css
--color-primary-50:  #f0fdfa
--color-primary-100: #ccfbf1
--color-primary-200: #99f6e4
--color-primary-300: #5eead4
--color-primary-400: #2dd4bf
--color-primary-500: #1a8f7a  ⭐ 메인 액센트
--color-primary-600: #0f766e
--color-primary-700: #0d5f57
--color-primary-800: #081f19  ⭐ 다크 그린
--color-primary-900: #002821  ⭐ 짙은 틸
```

### Secondary Colors
```css
--color-secondary-500: #0d8a61  ⭐ 성공
--color-secondary-600: #0a6b4d
--color-secondary-700: #07563f
```

### Semantic Colors
```css
--color-success:        #0d8a61  ✅
--color-success-light:  #d1fae5
--color-warning:        #f59e0b  ⚠️
--color-warning-light:  #fef3c7
--color-danger:         #ef4444  ❌
--color-danger-light:   #fee2e2
--color-info:           #3b82f6  ℹ️
--color-info-light:     #dbeafe
```

### Neutral Colors
```css
--color-gray-50:  #f8fafc  ⭐ 배경
--color-gray-100: #f1f5f9
--color-gray-200: #e2e8f0  ⭐ 테두리
--color-gray-300: #cbd5e1
--color-gray-400: #94a3b8
--color-gray-500: #64748b
--color-gray-600: #475569
--color-gray-700: #334155
--color-gray-800: #1e293b
--color-gray-900: #0f172a
```

### Text Colors
```css
--text-primary:   #111827  ⭐ 주요 텍스트
--text-secondary: #4a5568  ⭐ 보조 텍스트
--text-tertiary:  #718096  ⭐ 3차 텍스트
--text-inverse:   #ffffff  ⭐ 흰색 텍스트
```

### Background Colors
```css
--bg-primary:   #ffffff  ⭐ 주요 배경
--bg-secondary: #f8fafc  ⭐ 보조 배경
--bg-tertiary:  #f1f5f9
--bg-dark:      #081f19  ⭐ 다크 배경
--bg-darker:    #002821  ⭐ 더 다크 배경
```

---

## ✏️ Typography Tokens

### Font Families
```css
--font-family-base:    'Noto Sans KR', sans-serif
--font-family-heading: 'Noto Sans KR', sans-serif
--font-family-mono:    'SF Mono', monospace
```

### Font Sizes
```css
--font-size-xs:   0.75rem   /* 12px */
--font-size-sm:   0.875rem  /* 14px */
--font-size-base: 1rem      /* 16px ⭐ */
--font-size-lg:   1.125rem  /* 18px */
--font-size-xl:   1.25rem   /* 20px */
--font-size-2xl:  1.5rem    /* 24px */
--font-size-3xl:  1.875rem  /* 30px */
--font-size-4xl:  2.25rem   /* 36px */
--font-size-5xl:  3rem      /* 48px */
```

### Font Weights
```css
--font-weight-light:    300
--font-weight-normal:   400 ⭐
--font-weight-medium:   500
--font-weight-semibold: 600 ⭐
--font-weight-bold:     700 ⭐
```

### Line Heights
```css
--line-height-tight:    1.25  /* 제목 */
--line-height-normal:   1.5   ⭐ 본문
--line-height-relaxed:  1.75  /* 긴 텍스트 */
--line-height-loose:    2
```

### Letter Spacing
```css
--letter-spacing-tight:   -0.025em
--letter-spacing-normal:  0        ⭐
--letter-spacing-wide:    0.025em
--letter-spacing-wider:   0.05em
```

---

## 📏 Spacing Tokens

```css
--spacing-0:  0        /* 0px */
--spacing-1:  0.25rem  /* 4px */
--spacing-2:  0.5rem   /* 8px */
--spacing-3:  0.75rem  /* 12px */
--spacing-4:  1rem     /* 16px ⭐ 기본 */
--spacing-5:  1.25rem  /* 20px */
--spacing-6:  1.5rem   /* 24px */
--spacing-8:  2rem     /* 32px */
--spacing-10: 2.5rem   /* 40px */
--spacing-12: 3rem     /* 48px */
--spacing-16: 4rem     /* 64px */
--spacing-20: 5rem     /* 80px */
```

### 간격 사용 가이드
| 용도 | 토큰 | 크기 |
|------|------|------|
| 작은 간격 | `--spacing-2` | 8px |
| 기본 간격 | `--spacing-4` | 16px |
| 중간 간격 | `--spacing-6` | 24px |
| 큰 간격 | `--spacing-8` | 32px |
| 섹션 간격 | `--spacing-12` | 48px |

---

## 🔄 Border Radius

```css
--radius-none:  0
--radius-sm:    0.25rem  /* 4px */
--radius-base:  0.5rem   /* 8px ⭐ */
--radius-md:    0.75rem  /* 12px */
--radius-lg:    1rem     /* 16px */
--radius-xl:    1.5rem   /* 24px */
--radius-2xl:   2rem     /* 32px */
--radius-full:  9999px   /* 원형 */
```

---

## 🌥️ Shadows

```css
--shadow-xs:   0 1px 2px 0 rgba(0, 0, 0, 0.05)
--shadow-sm:   0 1px 3px 0 rgba(0, 0, 0, 0.1)
--shadow-base: 0 4px 6px -1px rgba(0, 0, 0, 0.1)  ⭐
--shadow-md:   0 10px 15px -3px rgba(0, 0, 0, 0.1)
--shadow-lg:   0 20px 25px -5px rgba(0, 0, 0, 0.1)
--shadow-xl:   0 25px 50px -12px rgba(0, 0, 0, 0.25)
--shadow-inner: inset 0 2px 4px 0 rgba(0, 0, 0, 0.06)
```

---

## ⚡ Transitions

```css
--transition-fast: 150ms cubic-bezier(0.4, 0, 0.2, 1)
--transition-base: 300ms cubic-bezier(0.4, 0, 0.2, 1)  ⭐
--transition-slow: 500ms cubic-bezier(0.4, 0, 0.2, 1)
```

---

## 📊 Z-Index

```css
--z-dropdown:        1000
--z-sticky:          1020
--z-fixed:           1030
--z-modal-backdrop:  1040
--z-modal:           1050
--z-popover:         1060
--z-tooltip:         1070
```

---

## 🎯 자주 사용하는 조합

### 버튼 스타일
```css
.btn-primary {
    background-color: var(--color-primary-500);
    color: var(--text-inverse);
    padding: var(--spacing-3) var(--spacing-6);
    border-radius: var(--radius-base);
    font-weight: var(--font-weight-semibold);
    transition: all var(--transition-fast);
}

.btn-primary:hover {
    background-color: var(--color-primary-600);
    box-shadow: var(--shadow-md);
    transform: translateY(-1px);
}
```

### 카드 스타일
```css
.card {
    background: var(--bg-primary);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-sm);
    padding: var(--spacing-6);
    transition: all var(--transition-base);
}

.card:hover {
    box-shadow: var(--shadow-lg);
    transform: translateY(-4px);
}
```

### 입력 필드 스타일
```css
.form-input {
    width: 100%;
    padding: var(--spacing-3) var(--spacing-4);
    border: 1px solid var(--color-gray-200);
    border-radius: var(--radius-base);
    font-size: var(--font-size-base);
    transition: all var(--transition-fast);
}

.form-input:focus {
    outline: none;
    border-color: var(--color-primary-500);
    box-shadow: 0 0 0 3px rgba(26, 143, 122, 0.1);
}
```

---

## 🔧 빠른 복사용 코드 조각

### 섹션 컨테이너
```css
.section {
    padding: var(--spacing-12) var(--spacing-8);
    background: var(--bg-secondary);
}

.section-title {
    font-size: var(--font-size-3xl);
    font-weight: var(--font-weight-bold);
    color: var(--color-primary-800);
    margin-bottom: var(--spacing-6);
}
```

### 그리드 레이아웃
```css
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-6);
}
```

### 플렉스 레이아웃
```css
.flex-center {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: var(--spacing-4);
}
```

---

## 📱 반응형 브레이크포인트

```css
/* Mobile First */
@media (min-width: 640px)  { /* sm */ }
@media (min-width: 768px)  { /* md */ }
@media (min-width: 1024px) { /* lg */ }
@media (min-width: 1280px) { /* xl */ }
```

---

## 🎨 색상 조합 추천

### Primary + Gray
```css
background: var(--bg-primary);
color: var(--text-primary);
accent: var(--color-primary-500);
```

### Dark Theme
```css
background: var(--color-primary-800);
color: var(--text-inverse);
accent: var(--color-primary-400);
```

### Success State
```css
background: var(--color-success-light);
color: var(--color-secondary-700);
border: var(--color-success);
```

---

**버전**: 1.0.0
**마지막 업데이트**: 2026-04-11

이 레퍼런스는 `design-system.css` 파일에 정의된 모든 디자인 토큰을 빠르게 찾을 수 있는 가이드입니다.
