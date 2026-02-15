---
name: ppt-design-system
description: "**PPT 한국형 디자인 시스템**: Pretendard + 명조체 조합의 프로페셔널 타이포그라피, 6:3:1 색상 법칙, 한국 비즈니스 PPT 레이아웃 가이드라인을 적용합니다. PptxGenJS 기반 코드 생성 시 자동으로 최적 디자인을 적용합니다.\n  - MANDATORY TRIGGERS: PPT 디자인, 슬라이드 디자인, 프레젠테이션 디자인, PPT 템플릿, 발표자료, 피치덱, pitch deck, PPT 폰트, 슬라이드 레이아웃"
---

# PPT 한국형 디자인 시스템

## Overview

한국 비즈니스 환경에 최적화된 PPT 디자인 시스템입니다.
Pretendard(고딕) + 조선일보명조(명조) 폰트 조합으로 전문적이고 가독성 높은 슬라이드를 생성합니다.

## 폰트 시스템

### 기본 폰트 (fonts/ 폴더에 포함)

| 폰트 | 용도 | 파일명 | Weight |
|-------|------|--------|--------|
| **Pretendard** | 고딕 (제목/본문/캡션) | Pretendard-{Weight}.otf | 9종: Thin(100)~Black(900) |
| **조선일보명조** | 명조 (인용/강조/격식) | ChosunilboNM.ttf | Regular |

### Pretendard 9종 Weight 가이드

| Weight | 파일명 | 용도 |
|--------|--------|------|
| Thin (100) | Pretendard-Thin.otf | 장식용 대형 텍스트, 워터마크 |
| ExtraLight (200) | Pretendard-ExtraLight.otf | 부제목(라이트 테마), 배경 텍스트 |
| Light (300) | Pretendard-Light.otf | 긴 본문, 설명 텍스트 |
| Regular (400) | Pretendard-Regular.otf | 기본 본문, 캡션 |
| Medium (500) | Pretendard-Medium.otf | 강조 본문, 라벨 |
| SemiBold (600) | Pretendard-SemiBold.otf | 소제목, 카드 제목 |
| Bold (700) | Pretendard-Bold.otf | 섹션 제목, 헤더 |
| ExtraBold (800) | Pretendard-ExtraBold.otf | 메인 제목, 슬라이드 타이틀 |
| Black (900) | Pretendard-Black.otf | KPI 숫자, 히어로 텍스트 |

### 폰트 적용 규칙

```
제목(Title):     Pretendard ExtraBold / Black    36~44pt
소제목(Subtitle): Pretendard SemiBold / Bold      24~28pt
본문(Body):      Pretendard Regular / Medium      16~20pt
캡션(Caption):   Pretendard Light / Regular       12~14pt
인용구(Quote):   조선일보명조 Regular              18~22pt (격식체, 인용문)
숫자강조(KPI):   Pretendard Black                  48~72pt
장식텍스트:      Pretendard Thin / ExtraLight      60~120pt (배경 대형 텍스트)
```

### 자간(Letter Spacing) & 줄간격(Line Height)

| 요소 | 자간 | 줄간격 | PptxGenJS 속성 |
|------|------|--------|----------------|
| 제목 | -0.5pt ~ 0pt | 1.1배 | `charSpacing: -0.5, lineSpacingMultiple: 1.1` |
| 소제목 | 0pt | 1.2배 | `lineSpacingMultiple: 1.2` |
| 본문 | 0.5pt ~ 1pt | 1.4~1.5배 | `charSpacing: 0.5, lineSpacingMultiple: 1.4` |
| 캡션 | 0.5pt | 1.3배 | `charSpacing: 0.5, lineSpacingMultiple: 1.3` |

## 색상 시스템 (6:3:1 법칙)

### 기본 팔레트: "Midnight Executive"

```javascript
const COLORS = {
  // 메인 60% - 배경/여백
  bg_primary:   'FFFFFF',  // 흰 배경
  bg_secondary: 'F5F7FA',  // 연한 회색 배경
  bg_dark:      '1A1F36',  // 다크 네이비 (표지/구분)
  
  // 보조 30% - 본문/구조
  text_primary:   '1A1F36', // 제목 텍스트 (다크 네이비)
  text_secondary: '4A5568', // 본문 텍스트 (차콜 그레이)
  text_tertiary:  '718096', // 캡션/보조 (미디엄 그레이)
  text_on_dark:   'FFFFFF', // 다크 배경 위 텍스트
  
  // 강조 10% - 포인트/CTA
  accent_blue:    '4A7BF7', // 메인 블루
  accent_cyan:    '00D4AA', // 시안 그린
  accent_yellow:  'FFB020', // 골드 옐로우
  accent_red:     'FF6B6B', // 경고/주의 레드
  accent_purple:  '8B5CF6', // 보조 퍼플
};
```

### 추가 팔레트 옵션

#### "Warm Corporate" (따뜻한 기업 톤)
```javascript
const WARM = {
  bg_dark: '2D1B4E', accent_blue: 'E8725A', accent_cyan: '4ECDC4',
  accent_yellow: 'F9C74F', accent_purple: '7B68EE'
};
```

#### "Nature Green" (친환경/ESG)
```javascript
const GREEN = {
  bg_dark: '1B3A2D', accent_blue: '2D9CDB', accent_cyan: '27AE60',
  accent_yellow: 'F2C94C', accent_red: 'EB5757'
};
```

#### "Minimal Mono" (미니멀)
```javascript
const MONO = {
  bg_dark: '111111', accent_blue: '333333', accent_cyan: '666666',
  accent_yellow: 'AAAAAA', text_primary: '111111'
};
```

## 레이아웃 시스템

### 슬라이드 크기
- **발표용**: 16:9 (기본값, 가로 13.33" × 세로 7.5")
- **인쇄/보고서용**: A4 (가로 11.69" × 세로 8.27")

### 여백 가이드 (16:9 기준)

```
┌─────────────────────────────────────┐
│  0.6"                         0.6"  │
│  ┌───────────────────────────────┐  │
│  │  콘텐츠 영역                  │  │  상단: 0.5"
│  │  가로: 12.13" / 세로: 6.5"   │  │
│  │                               │  │
│  └───────────────────────────────┘  │
│                                0.5" │  하단: 0.5"
└─────────────────────────────────────┘
```

| 영역 | 위치(x, y) | 크기(w, h) |
|------|-----------|-----------|
| 좌측 여백 | x=0.6" | - |
| 우측 여백 | - | w=12.13" (13.33-0.6-0.6) |
| 상단 여백 | y=0.5" | - |
| 하단 여백 | - | h=6.5" (7.5-0.5-0.5) |
| 페이지 번호 | x=12.3", y=7.1" | fontSize: 9pt |

### 핵심 레이아웃 패턴

#### 1. 표지 (Title Slide)
```
[다크 배경 전체]
  중앙: 과정명 (44pt ExtraBold, 흰색)
  중앙 아래: 부제목 (20pt Regular, 70% 흰색)
  하단: 발표자/날짜 (14pt, 50% 흰색)
```

#### 2. 섹션 구분 (Section Divider)
```
[좌측 40% 다크 배경 | 우측 60% 밝은 배경]
  좌측: 섹션 번호 (72pt Black, accent_cyan)
  우측: 섹션 제목 (36pt Bold) + 설명 (16pt Regular)
```

#### 3. 2단 콘텐츠 (Two Column)
```
[상단: 제목 바]
[좌측 50% | 우측 50%]
  각 컬럼: 소제목 (24pt Bold) + 본문 (16pt Regular)
  컬럼 간격: 0.4"
```

#### 4. 카드 그리드 (Card Grid)
```
[상단: 제목 바]
[2×2 또는 2×3 카드 그리드]
  카드: 둥근 모서리 (rectRadius=0.1)
  카드 간격: 0.3"
  카드 헤더: accent 색상 바 (높이 0.08")
```

#### 5. 타임라인 (Timeline)
```
[상단: 제목 바]
[좌측 색상 바 | 우측 항목 리스트]
  각 항목: 시간 (Bold) + 내용 (Regular) + 구분선
```

#### 6. KPI 대시보드 (Data Dashboard)
```
[상단: 제목 바]
[3~4열 KPI 카드]
  숫자: Pretendard Black 48pt (accent 색상)
  라벨: Regular 14pt (text_tertiary)
[하단: 차트/그래프 영역]
```

## PptxGenJS 코드 컨벤션

### 폰트 임베딩

```javascript
// Pretendard OTF 경로 (스킬 폴더 기준)
const FONT_DIR = path.join(__dirname, 'fonts');

// PptxGenJS에서 폰트 등록은 지원하지 않으므로
// 시스템에 Pretendard가 설치된 환경에서 다음과 같이 사용:
const FONTS = {
  title:    { fontFace: 'Pretendard', bold: true },   // ExtraBold/Black
  subtitle: { fontFace: 'Pretendard', bold: true },   // SemiBold/Bold
  body:     { fontFace: 'Pretendard', bold: false },   // Regular/Medium
  caption:  { fontFace: 'Pretendard', bold: false },   // Light/Regular
  serif:    { fontFace: 'ChosunilboNM', bold: false }, // 조선일보명조
  kpi:      { fontFace: 'Pretendard', bold: true },    // Black
  deco:     { fontFace: 'Pretendard', bold: false },   // Thin/ExtraLight (장식용)
};
```

### 슬라이드 생성 헬퍼

```javascript
// 표준 제목 바 추가 함수
function addTitleBar(slide, title, subtitle = '') {
  // 얇은 accent 라인
  slide.addShape('rect', {
    x: 0.6, y: 0.5, w: 1.2, h: 0.06,
    fill: { color: COLORS.accent_blue }
  });
  // 제목
  slide.addText(title, {
    x: 0.6, y: 0.65, w: 10, h: 0.6,
    fontSize: 28, fontFace: 'Pretendard', bold: true,
    color: COLORS.text_primary, charSpacing: -0.3
  });
  // 부제목 (있을 경우)
  if (subtitle) {
    slide.addText(subtitle, {
      x: 0.6, y: 1.25, w: 10, h: 0.4,
      fontSize: 16, fontFace: 'Pretendard',
      color: COLORS.text_tertiary
    });
  }
}

// 카드 생성 함수
function addCard(slide, { x, y, w, h, title, body, accentColor }) {
  // 카드 배경
  slide.addShape('roundRect', {
    x, y, w, h, rectRadius: 0.1,
    fill: { color: 'FFFFFF' },
    shadow: { type: 'outer', blur: 6, offset: 2, color: '00000015' }
  });
  // 상단 accent 바
  slide.addShape('rect', {
    x: x + 0.02, y, w: w - 0.04, h: 0.06,
    fill: { color: accentColor || COLORS.accent_blue }
  });
  // 카드 제목
  slide.addText(title, {
    x: x + 0.2, y: y + 0.2, w: w - 0.4, h: 0.35,
    fontSize: 16, fontFace: 'Pretendard', bold: true,
    color: COLORS.text_primary
  });
  // 카드 본문
  slide.addText(body, {
    x: x + 0.2, y: y + 0.55, w: w - 0.4, h: h - 0.75,
    fontSize: 13, fontFace: 'Pretendard',
    color: COLORS.text_secondary,
    lineSpacingMultiple: 1.4, valign: 'top'
  });
}

// 페이지 번호 추가
function addPageNumber(slide, num, total) {
  slide.addText(`${num} / ${total}`, {
    x: 12.0, y: 7.05, w: 1.0, h: 0.3,
    fontSize: 9, fontFace: 'Pretendard',
    color: COLORS.text_tertiary, align: 'right'
  });
}
```

## 6×6 콘텐츠 규칙

- 슬라이드 당 **글머리 기호 최대 6개**
- 글머리 당 **단어 6개 이내** (한글 기준 15~18자)
- 한 슬라이드에 **핵심 메시지 1개**
- 텍스트가 많으면 **2장으로 분할**

## 이미지 & 아이콘 가이드

### SVG 아이콘 사용
- 별도 `svg-diagram` 스킬을 활용하여 테마 색상에 맞는 SVG 아이콘/다이어그램 생성
- SVG → PNG 변환 후 삽입 (sharp 라이브러리 활용)

### Hero Image 규칙
- 한 슬라이드에 핵심 이미지 1개만 사용
- 이미지 선택 기준: 주제, 분위기, 해상도, 색상, 여백

## 2025-2026 한국형 PPT 디자인 트렌드

### 기능적 미니멀리즘
- 불필요한 장식 요소 배제, 콘텐츠 중심 디자인
- 넓은 여백(White Space) 적극 활용
- 한 슬라이드 = 한 메시지 원칙 강화
- 배경: 순백(#FFFFFF) 또는 연한 회색(#F5F7FA~#F8FAFC) 기본

### 모듈형 레이아웃
- 카드 기반 그리드 시스템 (2x2, 2x3, 1+2 변형)
- 각 모듈에 독립적 정보 단위 배치
- 모듈 간 일관된 간격(0.3"~0.4") 유지
- 반복 가능한 레이아웃 패턴으로 일관성 확보

### 포인트 컬러 전략
- 배경: 라이트 그레이 (#F5F7FA)
- 포인트: 네이비(#1A1F36) + 1~2가지 악센트 컬러
- 6:3:1 법칙: 배경 60% + 텍스트 30% + 강조 10%
- 그라데이션보다 단색(Flat) 선호

### 타이포그래피
- **Pretendard** — 한국 비즈니스 PPT 표준 폰트로 자리매김
- 가변폰트(Variable Font) 활용으로 세밀한 두께 조절
- 제목은 ExtraBold~Black, 본문은 Regular~Medium
- 자간: 제목 타이트(-0.5pt), 본문 약간 넓게(+0.5pt)
- 명조체(조선일보명조)는 인용구/강조에만 포인트 사용

### 데이터 시각화 강화
- 숫자 중심 KPI 카드 레이아웃 인기
- 복잡한 3D 차트 대신 2D 플랫 차트
- 아이콘 + 숫자 조합의 인포그래픽 스타일
- SVG 도식화 연계 (svg-diagram 스킬 활용)

## 체크리스트 (QA)

문서 생성 후 다음을 확인:
- [ ] 제목 36~44pt / 소제목 24~28pt / 본문 16~20pt 범위 내
- [ ] 자간: 제목 -0.5~0pt / 본문 0.5~1pt
- [ ] 줄간격: 본문 1.4배 이상
- [ ] 색상 6:3:1 비율 준수
- [ ] 여백: 좌우 0.6" / 상하 0.5" 이상
- [ ] 한 슬라이드 1 메시지 원칙
- [ ] 폰트 2종 이내 (Pretendard + 명조)
- [ ] 한글 깨짐 없음 (Pretendard 폰트 확인)
