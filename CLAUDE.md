# 사이버 모델하우스 프로젝트

## ⚠️ 중요: AI 작업 시 필독 사항

**이 프로젝트는 완성된 상태입니다. 아래 규칙을 반드시 준수하세요:**

### 🚫 절대 금지 사항
1. **코드 자동 수정 금지**: 사용자가 명시적으로 요청하지 않은 코드 변경 절대 금지
2. **구조 변경 금지**: HTML 구조, CSS 레이아웃, JavaScript 로직 임의 변경 금지
3. **라이브러리 변경 금지**: 현재 사용 중인 CDN/로컬 라이브러리 버전 유지
4. **색상 변경 금지**: 정의된 컬러 스킴(Premium Navy & Champagne Gold) 고수
5. **파일 추가/삭제 금지**: 기존 파일 구조 유지

### ✅ 허용되는 작업
1. **사용자 명시 요청**: 사용자가 구체적으로 요청한 수정만 진행
2. **버그 수정**: 명백한 오류(오타, 깨진 링크 등)는 사용자에게 제안 후 수정
3. **정보 제공**: 코드 설명, 구조 분석, 문제 진단 등

### 📋 작업 프로세스
```
1. 사용자 요청 확인
2. 현재 코드 상태 파악 (CLAUDE.md 참고)
3. 수정 계획 수립
4. 사용자에게 수정안 제시 및 승인 요청
5. 승인 후 수정 실행
6. 변경 사항 CLAUDE.md에 기록
```

---

## 📋 프로젝트 정보
- **프로젝트명**: 토지임대부 분양주택 사이버 모델하우스
- **GitHub**: https://github.com/jihun4170aa/samda-promo_test2.git
- **상태**: 완성 (Version 3.0.0)
- **메인 컬러**: Premium Navy (#1B2A4E) & Champagne Gold (#D4AF7A)
- **폰트**: Noto Sans KR (300, 400, 500, 700, 900)

---

## 🗂️ 파일 구조

```
6조2/
├── index.html                      # 메인 페이지 (fullPage.js 적용)
├── about.html                      # 사업안내 페이지
├── unit.html                       # 단지정보 페이지
├── plan.html                       # 세대안내 페이지 (인테리어 갤러리 포함)
├── sale.html                       # 분양안내 페이지
├── CLAUDE.md                       # 프로젝트 가이드 (본 문서)
├── Asset/                          # 이미지 리소스
│   ├── 조감도.png, 조감도6.png, 조감도8.png
│   ├── 49실내.png, 59실내.png
│   ├── 49인테리어 *.png (8개)
│   ├── 59인테리어 *.png (9개)
│   ├── 1지구 이미지.png, 2지구 이미지.png
│   └── 공사 한글로고(개정)-좌우조합.png
├── fullPage.js-2.9.7/             # fullPage.js 라이브러리 (로컬)
└── backup/                         # 백업 폴더
    ├── 20260602_172440/
    ├── 20260602_redesign/
    └── 20260611_interior_gallery/  # 최신 백업
```

---

## 🎨 현재 디자인 시스템

### 컬러 스킴 (Premium Navy & Champagne Gold)
```css
:root {
    --primary-color: #1B2A4E;           /* Deep Navy - 공공기관 신뢰감 */
    --primary-hover: #0F1933;           /* Darker Navy */
    --primary-light: #E8EBF0;           /* Light Navy-Gray */
    --accent-gold: #D4AF7A;             /* Champagne Gold */
    --accent-soft-gold: #E8D4B8;        /* Soft Gold */
    --accent-navy-gray: #E8EBF0;        /* Navy-Gray Tint */
    --dark-color: #1a1a1a;
    --gray-color: #666;
    --light-gray: #f8f9fa;
}
```

### Gradient 규칙
- **모든 gradient는 135도 각도로 통일**
- VR 섹션: `linear-gradient(135deg, var(--primary-color) 0%, var(--primary-hover) 50%, var(--accent-gold) 100%)`
- Footer: `linear-gradient(135deg, var(--primary-hover) 0%, var(--primary-color) 100%)`

### 헤더 구조 (모든 페이지 공통)
```css
.headerWrap {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 9999;
    background: white;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.header {
    max-width: 1900px;
    padding: 20px 80px 20px 40px;
    display: grid;
    grid-template-columns: 500px 1fr 150px;
    gap: 40px;
}
```

---

## 📄 페이지별 구조

### index.html (메인 페이지)
- **fullPage.js 2.9.7** 적용 (jQuery 기반)
- 5개 섹션: 메인 비주얼, 단지정보, VR, 로케이션, Footer
- 좌측 네비게이션 도트 (섹션별 이동)
- 모바일(768px)에서 일반 스크롤로 전환
- 네이버 지도 API 연동 (Client ID: `nticxunj9s`)

### about.html (사업안내)
- 사업개요, 사업위치, 입주자격 섹션
- AOS 애니메이션 적용
- 카드형 레이아웃

### unit.html (단지정보)
- 1지구/2지구 탭 전환
- 층별 세대 구성표 (테이블 형식)
- 핵심 특징 체크리스트

### plan.html (세대안내) ⭐ 최신 업데이트
- **4개 메인 탭**: 평면도, 인테리어, 사이버 모델하우스, 마감재
- **평면도 탭**: 49타입/59타입 서브탭 (상세 제원 테이블)
- **인테리어 탭**:
  - Swiper 갤러리 (17개 이미지)
  - 중앙 슬라이드 강조 (큰 사진 + 작은 사진들)
  - 무한 루프, 자동 재생
- **VR 탭**: 아이콘 그리드, CTA 버튼
- **마감재 탭**: 상세 마감재 테이블

### sale.html (분양안내)
- 분양일정: 수직 타임라인 (alternating layout)
- 입주자모집공고: 컬러 박스 레이아웃
- 청약안내: 가로 프로세스 플로우 (STEP 1-6)

---

## 🎯 주요 기능 및 라이브러리

### 사용 중인 라이브러리 (CDN)
```html
<!-- Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700;900&display=swap">

<!-- Icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<!-- Animation -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.js"></script>

<!-- Swiper -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css">
<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>

<!-- Naver Maps API -->
<script src="https://oapi.map.naver.com/openapi/v3/maps.js?ncpKeyId=nticxunj9s"></script>

<!-- jQuery (fullPage.js 의존성) -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
```

### 로컬 라이브러리
- **fullPage.js 2.9.7**: `fullPage.js-2.9.7/dist/jquery.fullpage.min.js`
  - index.html에만 적용
  - 섹션별 전체 스크롤
  - 좌측 네비게이션 도트

### Swiper 갤러리 설정 (plan.html 인테리어)
```javascript
new Swiper('.interior-swiper', {
    slidesPerView: 1.2,
    spaceBetween: 20,
    centeredSlides: true,
    loop: true,
    loopedSlides: 17,
    autoplay: { delay: 3000 },
    slideToClickedSlide: true,
    breakpoints: {
        640: { slidesPerView: 2.5 },
        1024: { slidesPerView: 3.5 },
        1400: { slidesPerView: 4 }
    }
});
```

**Swiper 스타일 (입체감)**
- 비활성 슬라이드: `scale(0.85)`, `opacity: 0.6`, 높이 350px
- 활성 슬라이드: `scale(1)`, `opacity: 1`, 높이 500px

---

## 📝 디자인 변경 이력

### Version 3.0.0 (2026-06-11)
**[인테리어 갤러리 추가 + 컬러 스킴 변경]**

**주요 변경사항:**
1. **컬러 스킴 변경** (모든 페이지)
   - Primary: #6B4E50 (갈색) → #1B2A4E (Premium Navy)
   - Accent: #D4AF7A (Champagne Gold) 신규 추가
   - 모든 gradient 135도로 통일

2. **plan.html 구조 수정**
   - type59를 floor-plan 내부 district-content로 재구조화
   - 탭 전환 오류 해결 (main-tab-content 구조 정리)

3. **인테리어 갤러리 추가** (plan.html)
   - Swiper 슬라이더 적용 (17개 인테리어 이미지)
   - 49타입 8개, 59타입 9개
   - 중앙 슬라이드 강조 (큰 사진 + 양옆 작은 사진)
   - 무한 루프, 자동 재생
   - 탭 활성화 시 Swiper 초기화 (지연 로딩)

4. **레이아웃 리디자인** (unit.html, plan.html, sale.html)
   - 단조로운 카드 레이아웃 → 다양한 형식으로 개선
   - 테이블, 타임라인, 프로세스 플로우, 넘버링 섹션 등

**영향 범위:**
- 모든 HTML 파일 (색상 변경)
- plan.html (구조 수정, 갤러리 추가)
- unit.html, sale.html (레이아웃 변경)

**백업:**
- `backup/20260611_interior_gallery/` - 전체 파일 백업 (44MB)

**Git 커밋:**
- `redesign: 단조로운 카드 레이아웃을 다양한 형식으로 개선` (cc266dc)
- `style: Premium Navy & Champagne Gold 컬러 스킴으로 변경` (aeb152b)
- `style: about.html 컬러 스킴 업데이트` (171910d)

---

### Version 2.0.0 (2026-05-30)
**[fullPage.js 적용]**
- fullPage.js 2.9.7 (jQuery 기반) 로컬 라이브러리 적용
- 좌측 네비게이션 도트 추가
- 섹션별 앵커 설정: home, unit, vr, location, footer
- 모바일(768px 이하)에서 일반 스크롤로 전환

---

## ⚠️ 중요 규칙

### 작업 전 체크사항
1. **백업 필수**: Major 변경 시 `backup/YYYYMMDD_작업명/` 폴더 생성
2. **커밋은 요청 시에만**: 사용자가 명시적으로 요청할 때만 Git 커밋
3. **구조 변경 주의**: HTML 구조 변경 시 탭 시스템 확인 필수
4. **색상 통일**: 모든 페이지 동일한 CSS 변수 사용
5. **Gradient 각도**: 항상 135도 사용

### 파일 수정 시 주의사항
- **plan.html**: main-tab-content 구조 확인 (floor-plan 내부에 type49, type59)
- **Swiper 초기화**: 탭 활성화 시점에 `initInteriorSwiper()` 호출
- **색상 변경**: :root 변수 사용, 하드코딩 금지

### 핵심 구조 (절대 변경 금지)

#### 1. 헤더 그리드 구조 (모든 페이지 공통)
```css
.header {
    display: grid;
    grid-template-columns: 500px 1fr 150px;  /* 로고 | GNB | 전화 */
    gap: 40px;
}
```

#### 2. GNB 메뉴 구조
```html
<nav>
    <ul id="gnb">
        <li><a>사업안내</a></li>
        <li><a>단지정보</a></li>
        <li><a>세대안내</a></li>
        <li><a>분양안내</a></li>
    </ul>
</nav>
<div class="submenu-area">
    <!-- 호버 시 전체 서브메뉴 표시 -->
</div>
```

#### 3. plan.html 탭 구조 (매우 중요!)
```html
<!-- 평면도 메인 탭 -->
<div class="main-tab-content active" id="floor-plan">
    <div class="tab-navigation">
        <button data-tab="type49">49타입</button>
        <button data-tab="type59">59타입</button>
    </div>
    <div class="district-content active" id="type49">...</div>
    <div class="district-content" id="type59">...</div>
    </div>  <!-- tab-navigation 닫기 -->
</div>

<!-- 인테리어 메인 탭 -->
<div class="main-tab-content" id="interior">
    <div class="interior-gallery">
        <div class="swiper interior-swiper">...</div>
    </div>
</div>
```

#### 4. Swiper 초기화 로직 (변경 금지)
```javascript
let interiorSwiper = null;
function initInteriorSwiper() {
    if (!interiorSwiper) {
        interiorSwiper = new Swiper('.interior-swiper', {
            slidesPerView: 1.2,
            centeredSlides: true,
            loop: true,
            loopedSlides: 17,
            // ... 나머지 설정
        });
    }
}

// 탭 클릭 시 호출
if (mainTabId === 'interior') {
    setTimeout(() => { initInteriorSwiper(); }, 100);
}
```

---

## 🔧 문제 해결 가이드

### Swiper가 안 보일 때
1. 탭이 hidden 상태에서 초기화되지 않았는지 확인
2. `initInteriorSwiper()` 함수가 탭 클릭 시 호출되는지 확인
3. 브라우저 콘솔에서 Swiper 관련 에러 확인

### 탭 전환이 안 될 때
1. `main-tab-content` 구조가 올바른지 확인
2. `data-maintab` 속성과 `id` 값이 일치하는지 확인
3. JavaScript 이벤트 리스너가 등록되었는지 확인

### 색상이 적용 안 될 때
1. `:root` 변수가 정의되어 있는지 확인
2. `var(--primary-color)` 형식으로 사용했는지 확인
3. 하드코딩된 색상 코드가 있는지 확인

---

**최종 수정일**: 2026-06-11
**현재 버전**: 3.0.0
**작성자**: Claude Code
