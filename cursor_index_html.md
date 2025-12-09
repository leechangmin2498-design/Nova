# Index.html 파일의 역할과 사용법
_Exported on 12/9/2025 at 11:28:10 GMT+9 from Cursor (2.1.50)_

---

**User**

@index.html 파일이 무엇을 할 때 쓰는 파일일까?

---

**Cursor**


`index.html` 내용 확인 중.



`index.html`은 웹 프로젝트의 기본 진입점입니다.

## 주요 용도:

1. **웹사이트의 홈페이지**: 브라우저가 도메인이나 폴더에 접근할 때 기본으로 표시되는 파일입니다.
   - 예: `https://example.com` → `https://example.com/index.html`을 자동으로 로드

2. **웹 서버의 기본 문서**: 대부분의 웹 서버는 디렉토리 요청 시 `index.html`을 기본 문서로 제공합니다.

3. **프로젝트의 시작점**: HTML, CSS, JavaScript를 포함한 웹 애플리케이션의 진입점입니다.

현재 파일이 비어 있으니, 필요하면 기본 HTML 구조를 추가할 수 있습니다. 원하시면 기본 템플릿을 만들어 드리겠습니다.

---

**User**

“새로운시작(New Star)”을알리는신제품, 신기술홍보용웹사이트를단일페이지웹앱으로만들어줄수있을까? 흔한디자인이어도상관없어. 그리고작업후결과를Report 폴더를만든후마크다운파일로만들어저장해줘.

---

**Cursor**


"새로운시작(New Star)" 신제품/신기술 홍보용 단일 페이지 웹앱을 만들고, 작업 결과를 Report 폴더의 마크다운 파일로 저장합니다.


```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>New Star - 새로운 시작</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            padding: 0.5rem 0;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #667eea;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: move 20s linear infinite;
        }

        @keyframes move {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            padding: 0 2rem;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.2s backwards;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeInUp 1s ease 0.4s backwards;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Section Styles */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
        }

        /* About Section */
        .about {
            background: #f8f9fa;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #666;
        }

        .about-image {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            height: 300px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        /* Features Section */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.15);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .feature-card p {
            color: #666;
            line-height: 1.6;
        }

        /* Technology Section */
        .technology {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .technology .section-title {
            color: white;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .tech-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .tech-item:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.2);
        }

        .tech-item h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }

        /* Contact Section */
        .contact {
            background: #f8f9fa;
        }

        .contact-content {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-top: 2rem;
        }

        .contact-form input,
        .contact-form textarea {
            padding: 1rem;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .contact-form button {
            padding: 1rem 2rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .contact-form button:hover {
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .nav-links {
                gap: 1rem;
                font-size: 0.9rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .features-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">⭐ New Star</div>
            <ul class="nav-links">
                <li><a href="#home">홈</a></li>
                <li><a href="#about">소개</a></li>
                <li><a href="#features">특징</a></li>
                <li><a href="#technology">기술</a></li>
                <li><a href="#contact">문의</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>새로운 시작, New Star</h1>
            <p>혁신적인 기술로 미래를 만들어갑니다</p>
            <a href="#about" class="cta-button">더 알아보기</a>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <h2 class="section-title">새로운 시작에 대해</h2>
        <div class="about-content">
            <div class="about-text">
                <p>
                    <strong>New Star</strong>는 혁신적인 기술과 창의적인 아이디어로 
                    새로운 가능성을 열어가는 신제품입니다. 우리는 고객의 삶을 더욱 
                    편리하고 풍요롭게 만들기 위해 최신 기술을 접목한 솔루션을 제공합니다.
                </p>
                <p style="margin-top: 1.5rem;">
                    지속 가능한 혁신과 사용자 중심의 디자인을 통해, 
                    단순한 제품을 넘어 경험을 제공하는 것이 우리의 목표입니다.
                </p>
            </div>
            <div class="about-image">
                🚀
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features">
        <h2 class="section-title">주요 특징</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <h3>초고속 성능</h3>
                <p>최신 기술로 구현된 뛰어난 성능으로 빠르고 효율적인 경험을 제공합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔒</div>
                <h3>안전한 보안</h3>
                <p>최고 수준의 보안 시스템으로 사용자의 데이터를 안전하게 보호합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎨</div>
                <h3>직관적 디자인</h3>
                <p>사용자 친화적인 인터페이스로 누구나 쉽게 사용할 수 있습니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🌐</div>
                <h3>글로벌 지원</h3>
                <p>전 세계 어디서나 접근 가능하며 다양한 언어를 지원합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">♻️</div>
                <h3>지속 가능성</h3>
                <p>환경을 고려한 친환경 기술로 지속 가능한 미래를 만들어갑니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🤝</div>
                <h3>24/7 지원</h3>
                <p>언제든지 도움이 필요하시면 전문가 팀이 지원해드립니다.</p>
            </div>
        </div>
    </section>

    <!-- Technology Section -->
    <section class="technology" id="technology">
        <h2 class="section-title">핵심 기술</h2>
        <div class="tech-grid">
            <div class="tech-item">
                <h3>인공지능</h3>
                <p>머신러닝과 딥러닝 기술</p>
            </div>
            <div class="tech-item">
                <h3>클라우드 컴퓨팅</h3>
                <p>확장 가능한 클라우드 인프라</p>
            </div>
            <div class="tech-item">
                <h3>블록체인</h3>
                <p>안전하고 투명한 데이터 관리</p>
            </div>
            <div class="tech-item">
                <h3>IoT 통합</h3>
                <p>스마트 디바이스 연결</p>
            </div>
            <div class="tech-item">
                <h3>빅데이터 분석</h3>
                <p>데이터 기반 인사이트 제공</p>
            </div>
            <div class="tech-item">
                <h3>모바일 최적화</h3>
                <p>모든 기기에서 완벽한 경험</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">문의하기</h2>
        <div class="contact-content">
            <p>New Star에 대해 더 궁금하신 점이 있으시면 언제든지 연락주세요.</p>
            <form class="contact-form" onsubmit="handleSubmit(event)">
                <input type="text" placeholder="이름" required>
                <input type="email" placeholder="이메일" required>
                <textarea rows="5" placeholder="메시지" required></textarea>
                <button type="submit">보내기</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 New Star. 새로운 시작을 함께합니다.</p>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission handler
        function handleSubmit(event) {
            event.preventDefault();
            alert('감사합니다! 곧 연락드리겠습니다.');
            event.target.reset();
        }

        // Fade in animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe feature cards
        document.querySelectorAll('.feature-card, .tech-item').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
```


Report 폴더를 생성하고 작업 결과를 마크다운 파일로 저장 중입니다.


```markdown
# New Star 웹사이트 프로젝트 보고서

## 프로젝트 개요
- **프로젝트명**: New Star - 새로운 시작
- **목적**: 신제품 및 신기술 홍보용 단일 페이지 웹 애플리케이션
- **작업일**: 2024년
- **파일 구조**: 단일 HTML 파일 (index.html)

## 구현 내용

### 1. 웹사이트 구조
단일 페이지 웹 애플리케이션으로 다음 섹션들을 포함합니다:

- **네비게이션 바**: 고정형 네비게이션으로 스크롤 시 스타일 변경
- **Hero 섹션**: 메인 비주얼 영역 (그라데이션 배경, 애니메이션 효과)
- **About 섹션**: New Star 소개
- **Features 섹션**: 6가지 주요 특징 카드
- **Technology 섹션**: 핵심 기술 소개
- **Contact 섹션**: 문의 폼
- **Footer**: 저작권 정보

### 2. 디자인 특징

#### 색상 스키마
- 메인 그라데이션: 보라색 계열 (#667eea → #764ba2)
- 배경: 흰색 및 연한 회색 (#f8f9fa)
- 텍스트: 진한 회색 (#333)

#### 주요 디자인 요소
- **그라데이션 배경**: Hero 섹션과 Technology 섹션에 적용
- **카드 디자인**: Features와 Technology 섹션에 호버 효과가 있는 카드
- **부드러운 애니메이션**: 
  - 페이드인 애니메이션
  - 스크롤 시 요소 등장 효과
  - 호버 시 카드 상승 효과
- **반응형 디자인**: 모바일, 태블릿, 데스크톱 지원

### 3. 기능 구현

#### JavaScript 기능
1. **스크롤 이벤트**: 네비게이션 바 스타일 변경
2. **부드러운 스크롤**: 앵커 링크 클릭 시 부드러운 스크롤 이동
3. **폼 제출 처리**: 문의 폼 제출 시 알림 표시
4. **Intersection Observer**: 스크롤 시 요소 페이드인 애니메이션

#### CSS 애니메이션
- Hero 섹션 배경 패턴 애니메이션
- 카드 호버 효과
- 버튼 호버 효과
- 페이드인/슬라이드업 애니메이션

### 4. 섹션별 상세 내용

#### Hero 섹션
- 메인 타이틀: "새로운 시작, New Star"
- 서브 타이틀: "혁신적인 기술로 미래를 만들어갑니다"
- CTA 버튼: "더 알아보기"

#### About 섹션
- New Star 소개 텍스트
- 시각적 요소 (이모지 아이콘)

#### Features 섹션 (6개)
1. ⚡ 초고속 성능
2. 🔒 안전한 보안
3. 🎨 직관적 디자인
4. 🌐 글로벌 지원
5. ♻️ 지속 가능성
6. 🤝 24/7 지원

#### Technology 섹션 (6개)
1. 인공지능
2. 클라우드 컴퓨팅
3. 블록체인
4. IoT 통합
5. 빅데이터 분석
6. 모바일 최적화

#### Contact 섹션
- 이름 입력 필드
- 이메일 입력 필드
- 메시지 입력 필드 (텍스트 영역)
- 제출 버튼

### 5. 반응형 디자인

#### 모바일 최적화 (768px 이하)
- Hero 타이틀 폰트 크기 조정 (4rem → 2.5rem)
- 네비게이션 링크 간격 축소
- About 섹션 그리드를 1열로 변경
- Features 그리드를 1열로 변경

### 6. 기술 스택

- **HTML5**: 시맨틱 마크업
- **CSS3**: 
  - Flexbox 및 Grid 레이아웃
  - CSS 애니메이션
  - 그라데이션 및 백드롭 필터
  - 미디어 쿼리 (반응형)
- **JavaScript (Vanilla)**:
  - DOM 조작
  - 이벤트 리스너
  - Intersection Observer API
  - 스크롤 이벤트 처리

### 7. 파일 구조

```
Nova/
├── index.html (단일 파일 - HTML, CSS, JavaScript 모두 포함)
└── Report/
    └── project-report.md (이 파일)
```

## 특징 및 장점

1. **단일 파일 구조**: 모든 코드가 하나의 HTML 파일에 포함되어 배포가 간단함
2. **외부 의존성 없음**: 별도의 CSS/JS 파일이나 라이브러리 불필요
3. **빠른 로딩**: 최소한의 리소스로 빠른 페이지 로드
4. **현대적인 디자인**: 그라데이션, 애니메이션, 카드 디자인 등 최신 웹 디자인 트렌드 반영
5. **사용자 경험**: 부드러운 스크롤, 호버 효과, 반응형 디자인으로 우수한 UX 제공

## 브라우저 호환성

- Chrome (최신 버전)
- Firefox (최신 버전)
- Safari (최신 버전)
- Edge (최신 버전)
- 모바일 브라우저 (iOS Safari, Chrome Mobile)

## 향후 개선 가능 사항

1. 다국어 지원 추가
2. 다크 모드 토글 기능
3. 실제 백엔드 연동 (폼 제출 처리)
4. 이미지 및 아이콘 추가 (현재는 이모지 사용)
5. SEO 최적화 (메타 태그 추가)
6. 성능 최적화 (이미지 최적화, 코드 분할 등)

## 사용 방법

1. `index.html` 파일을 웹 브라우저에서 열기
2. 또는 웹 서버에 업로드하여 배포

## 결론

"New Star - 새로운 시작" 신제품 홍보용 단일 페이지 웹 애플리케이션이 성공적으로 구현되었습니다. 현대적이고 반응형인 디자인으로 다양한 디바이스에서 최적의 사용자 경험을 제공하며, 신제품과 신기술을 효과적으로 소개할 수 있는 구조로 설계되었습니다.

```


작업 완료.

## 작업 완료 내역

### 1. **index.html** - "New Star" 단일 페이지 웹앱 생성
   - Hero 섹션: 그라데이션 배경과 애니메이션
   - About 섹션: 제품 소개
   - Features 섹션: 6가지 주요 특징 카드
   - Technology 섹션: 핵심 기술 소개
   - Contact 섹션: 문의 폼
   - 반응형 디자인: 모바일/태블릿/데스크톱 지원
   - 스크롤 애니메이션 및 호버 효과

### 2. **Report 폴더** 생성 및 보고서 작성
   - `Report/project-report.md` 파일 생성
   - 프로젝트 개요, 구현 내용, 기술 스택 등 포함

`index.html` 파일을 브라우저에서 열어 확인하세요. 모든 코드는 단일 HTML 파일에 포함되어 있어 별도의 설정 없이 바로 사용할 수 있습니다.

---

**User**

@https://kr.freepik.com/free-photo/beautiful-architecture-business-office-building-exterior_3717857.htm#fromView=keyword&page=1&position=0&uuid=49f313a1-ffc6-4d47-9f95-59fd4a600959&query=%EA%B8%B0%EC%97%85의이미지를기업이미지배경으로50% 투명도로설정해줘.

---

**Cursor**


기업 건물 이미지를 배경으로 50% 투명도로 적용. 현재 코드 확인 중.



기업 건물 이미지를 배경으로 50% 투명도로 적용. 이미지 파일을 프로젝트 폴더에 저장한 뒤 코드를 수정합니다.



기업 건물 이미지를 배경으로 50% 투명도로 적용 중. 이미지 파일명은 `background.jpg`로 가정합니다. 다른 이름이면 알려주세요.


```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>New Star - 새로운 시작</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
            position: relative;
        }

        /* 기업 이미지 배경 - 50% 투명도 */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('background.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            opacity: 0.5;
            z-index: -1;
        }

        /* 배경 이미지가 없을 경우를 대비한 대체 배경 */
        body::after {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #f5f5f5;
            z-index: -2;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            padding: 0.5rem 0;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #667eea;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: move 20s linear infinite;
        }

        @keyframes move {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            padding: 0 2rem;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.2s backwards;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeInUp 1s ease 0.4s backwards;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Section Styles */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
        }

        /* About Section */
        .about {
            background: #f8f9fa;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #666;
        }

        .about-image {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            height: 300px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        /* Features Section */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.15);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .feature-card p {
            color: #666;
            line-height: 1.6;
        }

        /* Technology Section */
        .technology {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .technology .section-title {
            color: white;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .tech-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .tech-item:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.2);
        }

        .tech-item h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }

        /* Contact Section */
        .contact {
            background: #f8f9fa;
        }

        .contact-content {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-top: 2rem;
        }

        .contact-form input,
        .contact-form textarea {
            padding: 1rem;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .contact-form button {
            padding: 1rem 2rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .contact-form button:hover {
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .nav-links {
                gap: 1rem;
                font-size: 0.9rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .features-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">⭐ New Star</div>
            <ul class="nav-links">
                <li><a href="#home">홈</a></li>
                <li><a href="#about">소개</a></li>
                <li><a href="#features">특징</a></li>
                <li><a href="#technology">기술</a></li>
                <li><a href="#contact">문의</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>새로운 시작, New Star</h1>
            <p>혁신적인 기술로 미래를 만들어갑니다</p>
            <a href="#about" class="cta-button">더 알아보기</a>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <h2 class="section-title">새로운 시작에 대해</h2>
        <div class="about-content">
            <div class="about-text">
                <p>
                    <strong>New Star</strong>는 혁신적인 기술과 창의적인 아이디어로 
                    새로운 가능성을 열어가는 신제품입니다. 우리는 고객의 삶을 더욱 
                    편리하고 풍요롭게 만들기 위해 최신 기술을 접목한 솔루션을 제공합니다.
                </p>
                <p style="margin-top: 1.5rem;">
                    지속 가능한 혁신과 사용자 중심의 디자인을 통해, 
                    단순한 제품을 넘어 경험을 제공하는 것이 우리의 목표입니다.
                </p>
            </div>
            <div class="about-image">
                🚀
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features">
        <h2 class="section-title">주요 특징</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <h3>초고속 성능</h3>
                <p>최신 기술로 구현된 뛰어난 성능으로 빠르고 효율적인 경험을 제공합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔒</div>
                <h3>안전한 보안</h3>
                <p>최고 수준의 보안 시스템으로 사용자의 데이터를 안전하게 보호합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎨</div>
                <h3>직관적 디자인</h3>
                <p>사용자 친화적인 인터페이스로 누구나 쉽게 사용할 수 있습니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🌐</div>
                <h3>글로벌 지원</h3>
                <p>전 세계 어디서나 접근 가능하며 다양한 언어를 지원합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">♻️</div>
                <h3>지속 가능성</h3>
                <p>환경을 고려한 친환경 기술로 지속 가능한 미래를 만들어갑니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🤝</div>
                <h3>24/7 지원</h3>
                <p>언제든지 도움이 필요하시면 전문가 팀이 지원해드립니다.</p>
            </div>
        </div>
    </section>

    <!-- Technology Section -->
    <section class="technology" id="technology">
        <h2 class="section-title">핵심 기술</h2>
        <div class="tech-grid">
            <div class="tech-item">
                <h3>인공지능</h3>
                <p>머신러닝과 딥러닝 기술</p>
            </div>
            <div class="tech-item">
                <h3>클라우드 컴퓨팅</h3>
                <p>확장 가능한 클라우드 인프라</p>
            </div>
            <div class="tech-item">
                <h3>블록체인</h3>
                <p>안전하고 투명한 데이터 관리</p>
            </div>
            <div class="tech-item">
                <h3>IoT 통합</h3>
                <p>스마트 디바이스 연결</p>
            </div>
            <div class="tech-item">
                <h3>빅데이터 분석</h3>
                <p>데이터 기반 인사이트 제공</p>
            </div>
            <div class="tech-item">
                <h3>모바일 최적화</h3>
                <p>모든 기기에서 완벽한 경험</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">문의하기</h2>
        <div class="contact-content">
            <p>New Star에 대해 더 궁금하신 점이 있으시면 언제든지 연락주세요.</p>
            <form class="contact-form" onsubmit="handleSubmit(event)">
                <input type="text" placeholder="이름" required>
                <input type="email" placeholder="이메일" required>
                <textarea rows="5" placeholder="메시지" required></textarea>
                <button type="submit">보내기</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 New Star. 새로운 시작을 함께합니다.</p>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission handler
        function handleSubmit(event) {
            event.preventDefault();
            alert('감사합니다! 곧 연락드리겠습니다.');
            event.target.reset();
        }

        // Fade in animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe feature cards
        document.querySelectorAll('.feature-card, .tech-item').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>

```


기업 건물 이미지를 배경으로 50% 투명도로 적용했습니다.

## 적용된 내용

1. **배경 이미지 설정**: `body::before`를 사용해 전체 페이지 배경에 이미지 적용
2. **50% 투명도**: `opacity: 0.5`로 설정
3. **고정 배경**: `background-attachment: fixed`로 스크롤 시 고정
4. **반응형**: 모든 화면 크기에 맞게 조정

## 다음 단계

Freepik에서 다운로드한 이미지를 프로젝트 폴더(`C:\DEV\Cursor_pro\Nova`)에 저장하세요.

**권장 파일명**: `background.jpg` (또는 `background.png`)

다른 파일명을 사용하려면 `index.html`의 다음 줄을 수정하세요:
```css
background-image: url('background.jpg');
```
→ 예: `background-image: url('office-building.jpg');`

이미지를 저장하면 자동으로 배경에 50% 투명도로 표시됩니다. 이미지가 없어도 페이지는 정상 작동하며, 흰색 배경이 표시됩니다.

```css
background-image: url('background.jpg');
```

