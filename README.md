# 청첩장 전자책 뷰어

부산에서 놓고 온 청첩장을 전자책 형태로 볼 수 있는 웹 애플리케이션입니다.

## 📱 주요 기능

- **페이지 넘김 효과**: 실제 책을 넘기는 듯한 자연스러운 애니메이션
- **모바일 최적화**: 스와이프 제스처로 직관적인 페이지 이동
- **반응형 디자인**: 모바일/데스크탑 모두 지원
- **우아한 UI**: 검은 배경에 떠있는 청첩장 북
- **QR 코드 리다이렉트**: inside1의 QR 코드 클릭 시 모바일 청첩장으로 이동
- **스마트 레이아웃**: 데스크탑에서 펼친 페이지 자동 가운데 정렬

## 📂 파일 구조

프로젝트 루트에 다음 이미지 파일들을 배치하세요:

```
wedding-invitation-ebook/
├── index.html
├── vercel.json
├── package.json
├── cover1.jpg      # 청첩장 앞표지
├── inside1.jpg      # 첫 번째 내지
├── inside2.jpg      # 두 번째 내지
└── cover2.jpg      # 청첩장 뒤표지
```

## 🚀 Vercel 배포 방법

### 1. Vercel CLI 사용

```bash
# Vercel CLI 설치 (처음 한 번만)
npm install -g vercel

# 프로젝트 디렉토리에서 배포
vercel

# 프로덕션 배포
vercel --prod
```

### 2. Vercel 웹 대시보드 사용

1. [Vercel](https://vercel.com)에 로그인
2. "New Project" 클릭
3. GitHub 저장소 연결 또는 파일 직접 업로드
4. 자동으로 감지된 설정 확인 후 Deploy 클릭

### 3. GitHub를 통한 자동 배포 (권장)

1. GitHub에 저장소 생성
2. 파일들을 푸시:

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin [your-repo-url]
git push -u origin main
```

3. Vercel에서 GitHub 저장소 import
4. 이후 push할 때마다 자동 배포

## 🎨 사용 방법

### 모바일

- **좌우 스와이프**: 페이지 넘기기
- **하단 버튼**: 이전/다음 페이지 이동

### 데스크탑

- **클릭**: 하단 화살표 버튼으로 이동
- **키보드**: 좌우 화살표 키로 페이지 넘기기

## 🎯 페이지 순서

1. cover1 (앞표지)
2. inside1 (첫 번째 내지)
3. inside2 (두 번째 내지)
4. cover2 (뒤표지)

## ⚙️ 커스터마이징

### QR 코드 리다이렉트 URL 설정

`index.html` 파일에서 다음 부분을 수정하세요:

```javascript
// 47번째 줄 근처
const qrRedirectUrl = "https://example.com/mobile-invitation"; // 실제 모바일 청첩장 URL로 변경
```

### QR 클릭 영역 위치 조정

inside1의 QR 코드 위치가 다른 경우, CSS를 수정하세요:

```css
/* QR 코드 클릭 영역 */
.qr-clickable {
  width: 40%; /* 영역 크기 */
  height: 40%; /* 영역 크기 */
  top: 50%; /* 상하 위치 (50% = 중앙) */
  left: 50%; /* 좌우 위치 (50% = 중앙) */
}
```

### 이미지 파일명 변경이 필요한 경우

`index.html` 파일에서 다음 부분을 수정하세요:

```javascript
const pages = [
  { id: 0, image: "cover1.jpg" },
  { id: 1, image: "inside1.jpg" },
  { id: 2, image: "inside2.jpg" },
  { id: 3, image: "cover2.jpg" },
];

// 예: PNG 파일인 경우
const pages = [
  { id: 0, image: "cover1.png" },
  { id: 1, image: "inside1.png" },
  { id: 2, image: "inside2.png" },
  { id: 3, image: "cover2.png" },
];
```

### 페이지 크기 조정

CSS 변수를 수정하세요:

```css
:root {
  --page-width: min(90vw, 400px);
  --page-height: calc(var(--page-width) * 1.414); /* A3 비율 */
}
```

## 🔧 문제 해결

### 이미지가 보이지 않을 때

- 파일명이 정확한지 확인 (대소문자 구분)
- 파일 확장자 확인 (.jpg, .jpeg, .png 등)
- 브라우저 개발자 도구에서 네트워크 에러 확인

### 페이지 넘김이 작동하지 않을 때

- JavaScript 오류가 있는지 콘솔 확인
- 브라우저가 최신 버전인지 확인

## 📝 라이선스

개인 사용 목적으로 자유롭게 사용하세요.
