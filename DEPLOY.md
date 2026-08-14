# 배포 체크리스트

기준일: 2026-07-06

## 업로드해야 하는 파일

필수:
- index.html
- manifest.webmanifest
- sw.js
- icon.svg

권장:
- _redirects
- netlify.toml
- vercel.json
- firebase.json

로컬 실행용:
- server.js
- package.json

## 가장 쉬운 배포

Netlify 드래그앤드롭 배포가 가장 빠릅니다.

1. ZIP 압축 해제
2. 폴더 전체를 Netlify에 드래그앤드롭
3. 생성된 URL 공유

## 운영 메모

- API 키 없음
- 백엔드 서버 없음
- 사용자는 URL 접속만 하면 사용 가능
- 첫 실행 시 모델 다운로드 때문에 시간이 걸릴 수 있음

## v4.4 추가

- 메인 문구를 `Remover studio`로 변경
- 누끼 엔진은 v4.3 기준 그대로 유지
