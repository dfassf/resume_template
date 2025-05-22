# Vue.js 기반 이력서 템플릿

제 이력서를 만들면서 겸사겸사 템플릿화 하였습니다. 제가 가장 잘 다루는 Vue.js 기반으로 커스터마이징 가능하도록 제작했습니다. 토스(Toss)의 심플하고 세련된 UI 디자인과 컬러 시스템을 차용하였습니다.

## 주요 기능

- 📱 모든 디바이스에 최적화된 반응형 디자인
- 🎯 Vue.js 데이터 객체 기반 관리로 쉬운 내용 수정
- ✨ 스크롤에 반응하는 애니메이션 효과 (Vue + GSAP)
- 🖼️ 포트폴리오 이미지 갤러리 및 확대 기능
- 🧩 모듈화된 Vue.js 컴포넌트 구조
- 🎨 토스 스타일의 미니멀한 디자인 시스템 적용

## 시작하기

### 필수 요구사항

- 웹 브라우저 (Chrome, Firefox, Safari, Edge 최신 버전 권장)
- 기본적인 HTML, CSS, JavaScript 및 Vue.js 이해
- GitHub 계정 (GitHub Pages 배포용)

### 설치 및 배포 방법

1. 이 저장소를 클론합니다:
```
git clone https://github.com/dfassf/resume_template.git
cd resume_template
```

2. Git 저장소를 초기화하고 자신의 GitHub 저장소로 설정합니다:
```
# 기존 .git 디렉토리 삭제
rm -rf .git

# 새 Git 저장소 초기화
git init

# GitHub에서 새 저장소를 생성한 후, 원격 저장소로 추가 (YOUR_USERNAME을 자신의 GitHub 사용자명으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

3. 자신의 정보로 `index.html` 파일의 데이터 객체를 수정합니다.

4. 변경사항을 커밋하고 GitHub에 푸시합니다:
```
git add .
git commit -m "이력서 내용 업데이트"
git branch -M main
git push -u origin main
```

5. GitHub Pages를 통해 배포하기:
   - GitHub 저장소 페이지로 이동합니다
   - Settings > Pages 메뉴로 이동합니다
   - Source 섹션에서 Branch를 'main'으로 선택합니다
   - Save 버튼을 클릭합니다
   - 잠시 후 웹사이트가 `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY` 주소로 배포됩니다

6. 배포된 이력서에 접속하여 모든 기능이 정상적으로 작동하는지 확인합니다.

## 내용 커스터마이징

Vue.js의 강력한 데이터 바인딩 기능을 활용하여 `index.html` 파일 내의 Vue 인스턴스 데이터 객체만 수정하면 전체 이력서 내용이 자동으로 업데이트됩니다:

### 기본 데이터 수정 방법

```javascript
data: {
    personalInfo: {
        name: '홍길동', // 이름 변경
        position: 'IT 전문가' // 직위 변경
    },
    // 다른 섹션도 비슷한 방식으로 수정
}
```

### 데이터 구조 및 활용법

이 템플릿은 Vue.js의 데이터 기반 렌더링을 최대한 활용합니다:

1. **배열 데이터 활용**:
   ```javascript
   // 기술 스택 항목 추가/수정/삭제
   skillsSection: {
     categories: [
       {
         name: '프로그래밍 언어',
         skills: ['JavaScript', 'Python', 'Java'] // 이 배열에 항목을 추가하거나 제거
       }
     ]
   }
   ```

2. **섹션 표시/숨김 제어**:
   ```javascript
   // 특정 섹션을 비활성화하려면 해당 객체를 null로 설정하거나 visible 속성을 추가
   portfolioSection: null, // 포트폴리오 섹션 비활성화
   
   // 또는
   educationSection: {
     visible: false, // 교육 섹션 숨김
     title: '학력 및 자격증',
     // ...나머지 속성들
   }
   ```

3. **타이핑 효과 및 커서 제어**:
   ```javascript
   // 타이핑 효과와 커서를 제어하는 옵션
   typingOptions: {
     showCursor: false, // 커서 숨기기
     enableTyping: false // 타이핑 효과 비활성화 (텍스트가 바로 표시됨)
   }
   ```

4. **메뉴 항목 관리**:
   ```javascript
   // 메뉴 항목 추가/제거/변경
   menuItems: [
     { id: 'home', text: '프로필', href: '#' },
     { id: 'about', text: '소개', href: '#about' },
     // 새 항목 추가 또는 기존 항목 제거
   ]
   ```

5. **복잡한 중첩 데이터**:
   ```javascript
   // 경력 항목에 새 회사 추가
   experienceSection: {
     companies: [
       // 기존 회사 데이터,
       {
         name: '새 회사명',
         logoSrc: 'assets/company_logos/logo.png',
         duration: '20XX.01 - 20XX.12',
         // ...다른 속성들
       }
     ]
   }
   ```

동적 데이터 관리는 이력서의 모든 부분을 Vue 인스턴스 내의 데이터로 제어함으로써, HTML 코드를 직접 수정하지 않고도 내용을 완전히 커스터마이징할 수 있게 합니다.

### 주요 섹션 구성

- **personalInfo**: 이름, 직위 등 기본 정보
- **heroSection**: 메인 소개 섹션
- **aboutSection**: 자기소개 섹션
- **experienceSection**: 경력 정보
- **portfolioSection**: 포트폴리오 프로젝트
- **skillsSection**: 기술 스택
- **educationSection**: 학력 및 자격증
- **contactSection**: 연락처 정보
- **footerSection**: 푸터 정보

## 이미지 변경하기

포트폴리오 및 회사 로고 이미지는 다음 위치에 저장해야 합니다:

- 회사 로고: `assets/company_logos/`
- 포트폴리오 이미지: `assets/portfolios/프로젝트명/`

이미지 경로는 Vue 데이터 객체에서 변경할 수 있습니다:

```javascript
experienceSection: {
    companies: [
        {
            logoSrc: 'assets/company_logos/회사로고.png',
            // 다른 정보들...
        }
    ]
}
```

## 스타일 커스터마이징

스타일 수정은 `style.css` 파일에서 가능합니다. 주요 스타일 섹션은 다음과 같이 구성되어 있습니다:

- 전역 스타일 및 변수
- 헤더 및 내비게이션
- 각 섹션별 스타일
- 반응형 미디어 쿼리

## 라이선스

이 프로젝트는 MIT 라이선스에 따라 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 기여하기

이슈 및 풀 리퀘스트를 통한 기여를 환영합니다. 기능 개선이나 버그 수정 제안은 이슈를 통해 알려주세요.

## 디자인 특징

이 이력서 템플릿은 토스(Toss)의 미니멀하고 세련된 UI/UX 디자인 철학을 차용했습니다:

- 깔끔한 타이포그래피와 여백 활용
- 직관적인 시각적 계층 구조
- 부드러운 애니메이션과 전환 효과
- 간결하고 목적에 충실한 컬러 시스템
- 사용자 액션에 대한 미묘하지만 효과적인 피드백

## 크레딧

- 템플릿 디자인 및 개발: [엄신우](https://github.com/dfassf)
- UI 디자인 영감: 토스(Toss)
- 아이콘: SVG 아이콘
- 폰트: Pretendard

---

💼 **멋진 이력서로 더 나은 커리어를 시작하세요!** 