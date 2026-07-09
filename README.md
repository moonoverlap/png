# PNG 배경 제거기 v1.5 배포용

기준일: 2026-07-06

## 수정 내용

- 상단 안내 문구 삭제
  - `v1.4 원본 해상도 저장`
  - `다운로드 PNG를 원본 픽셀 기준으로 저장하고 2배/4배 저장 옵션을 추가했습니다.`
- 어디서든 사용할 수 있도록 정적 배포용 파일 추가
  - `manifest.webmanifest`
  - `sw.js`
  - `icon.svg`
  - `netlify.toml`
  - `vercel.json`
  - `firebase.json`
  - `_redirects`
- 기존 기능 유지
  - 배경만 제거
  - AI 피사체 인식
  - 처리 품질: 빠름 / 표준 / 고품질
  - 저장 해상도: 원본 / 2배 / 4배
  - 저장 파일명: `_t.png`

## 로컬 실행

```bash
npm start
```

브라우저 접속:

```text
http://localhost:5173
```

## 어디서든 쓰는 방법

이 앱은 서버 프로그램 없이 `index.html` 중심으로 동작하는 정적 웹앱입니다. 아래 중 하나에 올리면 PC, 모바일, 태블릿에서 주소로 접속해 사용할 수 있습니다.

### 1. Netlify

1. Netlify에 로그인
2. `Add new site` 선택
3. 이 폴더를 드래그앤드롭
4. 생성된 URL로 접속

### 2. Vercel

1. GitHub에 이 폴더 업로드
2. Vercel에서 프로젝트 Import
3. Framework Preset은 `Other`
4. Build Command는 비워둠
5. Output Directory는 `.`
6. Deploy

### 3. Firebase Hosting

```bash
firebase login
firebase init hosting
firebase deploy
```

이미 `firebase.json`이 포함되어 있어 Hosting 기준으로 바로 배포할 수 있습니다.

## 주의사항

- 첫 실행 시 AI 모델 파일을 인터넷에서 내려받습니다.
- 완전 오프라인 앱은 아닙니다.
- 한 번 로딩된 앱 화면은 서비스워커 캐시가 적용될 수 있습니다.
- 이미지 처리는 브라우저에서 수행됩니다.
