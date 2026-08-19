# v89 무료 RMBG API 모드 배포

## 포함 내용

- GitHub Pages용 프론트: `index.html`, `api-config.js`
- 무료 AI 누끼 서버 예제: `hf-space-rmbg-api/`
- 기본 흐름: 무료 RMBG API 우선 → 실패 시 브라우저 로컬 AI 자동 대체

## 1. 무료 AI 서버 만들기

Hugging Face Space에서 Docker Space를 만들고 `hf-space-rmbg-api` 폴더의 파일을 업로드합니다.

빌드 완료 후 엔드포인트:

```text
https://내아이디-스페이스이름.hf.space/remove-bg
```

## 2. 프론트에 서버 주소 입력

`api-config.js` 수정:

```js
window.RMBG_API_URL = "https://내아이디-스페이스이름.hf.space/remove-bg";
```

앱 화면의 `무료 AI 서버 URL` 입력칸에 직접 넣어도 됩니다.

## 3. GitHub Pages 배포

```powershell
cd "C:\Users\user\OneDrive\Desktop\압축파일\image-toolkit-v89-free-rmbg-api-mode"

if (Test-Path .\_deploy_png) { Remove-Item -Recurse -Force .\_deploy_png }

git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git hf-space-rmbg-api /XF *.zip

cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Add free RMBG API mode"
git push origin main
```

주의: `hf-space-rmbg-api`는 Hugging Face Space용 서버 코드라서 GitHub Pages 저장소에는 올리지 않아도 됩니다.
