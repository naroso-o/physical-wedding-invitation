# 청첩장 전자책 뷰어

부산에서 놓고 온 청첩장을 전자책 형태로 볼 수 있는 웹 애플리케이션입니다.

## 📱 주요 기능

- **페이지 넘김 효과**: 실제 책을 넘기는 듯한 3D 애니메이션
- **모바일 최적화**: 스와이프 제스처로 직관적인 페이지 이동
- **반응형 디자인**: 모바일/데스크탑 모두 지원
- **우아한 UI**: 검은 배경에 떠있는 청첩장 북

## 📂 파일 구조

프로젝트 루트에 다음 이미지 파일들을 배치하세요:

```
wedding-invitation-ebook/
├── index.html
├── vercel.json
├── package.json
├── 겉지1.jpg      # 청첩장 앞표지
├── 속지1.jpg      # 첫 번째 내지
├── 속지2.jpg      # 두 번째 내지
└── 겉지2.jpg      # 청첩장 뒤표지
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

1. 겉지1 (앞표지)
2. 속지1 (첫 번째 내지)
3. 속지2 (두 번째 내지)
4. 겉지2 (뒤표지)

## ⚙️ 커스터마이징

### 이미지 파일명 변경이 필요한 경우

`index.html` 파일에서 다음 부분을 수정하세요:

```javascript
const pages = [
    { front: '겉지1.jpg', back: '속지1.jpg' },
    { front: '속지2.jpg', back: '겉지2.jpg' }
];
```

### 페이지 크기 조정

CSS 변수를 수정하세요:

```css
:root {
    --page-width: min(90vw, 400px);
    --page-height: calc(var(--page-width) * 1.414);  /* A3 비율 */
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
