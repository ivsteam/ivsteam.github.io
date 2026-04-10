# 인베슘 웹사이트 (Invesume Website)

인베슘(Invesume) 공식 웹사이트입니다. 오픈소스 전문 기업으로서의 회사 소개, 제품 & 서비스, 고객사 사례, 뉴스 등을 제공합니다.

## 기술 스택

- **Hugo**: 정적 사이트 생성기 (v0.125+)
- **Bootstrap 5**: CSS 프레임워크
- **Font Awesome 6**: 아이콘 라이브러리
- **AOS**: 스크롤 애니메이션 라이브러리
- **Google Fonts**: Noto Sans KR, Roboto

## 프로젝트 구조

```
ivsteam.github.io/
├── assets/              # Hugo 파이프라인용 자산
├── content/             # 콘텐츠 파일 (마크다운)
│   ├── _index.md       # 메인 페이지 (한국어)
│   ├── en/              # 영어 콘텐츠
│   ├── about/           # 회사소개
│   ├── products/        # 제품 & 서비스
│   ├── customers/       # 고객사
│   ├── news/            # 뉴스
│   └── contact/         # 연락처
├── layouts/             # HTML 템플릿
│   ├── _default/       # 기본 템플릿
│   ├── partials/       # 재사용 가능한 컴포넌트
│   └── products/       # 제품 페이지 템플릿
├── static/              # 정적 파일
│   ├── css/            # 커스텀 CSS
│   ├── js/             # 자바스크립트
│   ├── img/            # 이미지
│   └── fonts/          # 폰트
├── hugo.toml           # Hugo 설정 파일
└── README.md           # 이 파일
```

## 로컬 개발 환경 설정

### 1. Hugo 설치

#### Linux (Ubuntu/Debian)
```bash
# Hugo 다운로드 및 설치
wget https://github.com/gohugoio/hugo/releases/download/v0.125.0/hugo_extended_0.125.0_linux-amd64.deb
sudo dpkg -i hugo_extended_0.125.0_linux-amd64.deb

# 또는 snap으로 설치
sudo snap install hugo
```

#### macOS
```bash
# Homebrew로 설치
brew install hugo
```

#### Windows
```bash
# Chocolatey로 설치
choco install hugo-extended

# 또는 Scoop으로 설치
scoop install hugo-extended
```

### 2. 개발 서버 시작

```bash
# 프로젝트 디렉토리로 이동
cd /home/hamonikr/work/ivsteam.github.io

# Hugo 개발 서버 시작
hugo server

# 또는 특정 포트로 실행
hugo server --port 1313

# 또는 모든 네트워크 인터페이스에 바인딩
hugo server --bind 0.0.0.0 --baseURL=http://your-ip:1313
```

서버가 시작되면 http://localhost:1313 에서 웹사이트를 확인할 수 있습니다.

### 3. 라이브 리로드

Hugo 개발 서버는 자동으로 파일 변경을 감지하고 브라우저를 새로고침합니다:
- 콘텐츠 변경 시 즉시 반영
- 템플릿 변경 시 즉시 반영
- CSS/JS 변경 시 즉시 반영

## 콘텐츠 관리

### 새로운 뉴스 추가

```bash
# 1. 새 뉴스 파일 생성
hugo new news/새로운-소식.md

# 2. 파일 편집 (content/news/새로운-소식.md)
---
title: "새로운 소식 제목"
date: 2025-04-10
draft: false
category: "보도자료"
description: "요약 설명"
image: "/img/news/news-image.jpg"
---

뉴스 내용을 여기에 작성합니다...
```

### 제품 정보 수정

- **제품 목록**: `content/products/_index.md`
- **개별 제품**: `content/products/` 폴더의 각 마크다운 파일
- **오픈소스 프로젝트**: `layouts/products/list.html`의 오픈소스 섹션 수정

### 다국어 콘텐츠

영어 콘텐츠는 `content/en/` 폴더에 관리합니다:
```
content/
├── _index.md        # 한국어 메인
├── en/
│   ├── _index.md    # 영어 메인
│   ├── about.md     # 영어 회사소개
│   └── products.md  # 영어 제품
```

## 스타일 커스터마이징

### 메인 컬러 변경

`static/css/custom.css`의 CSS 변수 수정:

```css
:root {
    --primary-color: #081f19;      /* 메인 컬러 */
    --accent-color: #1a8f7a;       /* 강조 컬러 */
    --success-color: #0d8a61;      /* 성공 컬러 */
    /* ... 다른 변수들 */
}
```

### 버튼 스타일

모든 버튼은 사이트 컬러로 자동 적용됩니다 (`btn-primary`, `btn-outline-primary`).

## 템플릿 수정

### 메인 페이지

- **한국어**: `layouts/index.html`의 `{{ else }}` 섹션
- **영어**: `layouts/index.html`의 `{{ if eq .Lang "en" }}` 섹션

### 섹션 페이지

- **고객사**: `layouts/_default/list.html`의 customers 섹션
- **제품**: `layouts/products/list.html`

### 컴포넌트

- **헤더/네비게이션**: `layouts/partials/header.html`
- **푸터**: `layouts/partials/footer.html`

## 빌드 및 배포

### 프로덕션 빌드

```bash
# 정적 사이트 빌드
hugo

# 출력: public/ 디렉토리
```

### GitHub Pages 배포

```bash
# 1. 변경사항 커밋
git add .
git commit -m "Update content"

# 2. 메인 브랜치에 푸시
git push origin master

# 3. GitHub Actions가 자동으로 배포합니다
```

### 수동 배포

```bash
# public/ 디렉토리의 내용을 웹 서버에 업로드
# 예: rsync, scp, FTP 등
rsync -avz public/ user@server:/var/www/html/
```

## 유지관리 가이드

### 정기 점검 항목

1. **월간**
   - [ ] 뉴스/소식 업데이트
   - [ ] 콘텐츠 링크 확인
   - [ ] 이미지 최적화

2. **분기별**
   - [ ] Hugo 버전 업데이트 확인
   - [ ] 의존성 라이브러리 업데이트 (Bootstrap, AOS 등)
   - [ ] SEO 메타데이터 검토

3. **연간**
   - [ ] 디자인 트렌드 반영 검토
   - [ ] 웹사이트 성능 최적화
   - [ ] 액세서빌리티 점검

### 이미지 관리

- **권장 크기**: 최대 2000px 너비
- **권장 형식**: JPG (사진), PNG (로고/아이콘), WebP (최적화)
- **저장 위치**: `static/img/` 하위 폴더별 분류

```bash
# 이미지 최적화 예시 (ImageMagick 사용)
convert input.jpg -quality 85 -resize 1920x output.jpg
```

### SEO 최적화

각 페이지의 메타데이터 확인:

```yaml
---
title: "페이지 제목"
description: "페이지 설명 (150자 이내)"
keywords: ["키워드1", "키워드2"]
image: "/img/og-image.jpg"
---
```

## 문제 해결

### 일반적인 문제

**문제**: 변경사항이 반영되지 않음
```bash
# 해결: Hugo 캐시 삭제
rm -rf resources/
hugo server
```

**문제**: 빌드 실패
```bash
# 해결: 의존성 재설치
hugo mod clean
hugo mod tidy
```

**문제**: 스타일이 적용되지 않음
```bash
# 해결: CSS 버전 번호 업데이트
# layouts/partials/header.html에서 버전 번호 변경
<link href="/css/custom.css?v=18" rel="stylesheet">
```

### 개발자 도구

브라우저 개발자 도구(F12) 사용:
- **콘솔**: JavaScript 오류 확인
- **네트워크**: 리소스 로딩 확인
- **요소**: CSS 스타일 검사

## 기여 가이드

1. 새로운 브랜치 생성: `git checkout -b feature/your-feature`
2. 변경사항 커밋: `git commit -m "Add your feature"`
3. 브랜치 푸시: `git push origin feature/your-feature`
4. Pull Request 생성

## 라이선스

이 프로젝트는 인베슘(Invesume)의 자산입니다.

## 연락처

- **웹사이트**: https://invesume.com
- **이메일**: hckim@invesume.com
- **GitHub**: https://github.com/ivsteam

---

**마지막 업데이트**: 2025년 4월 10일
