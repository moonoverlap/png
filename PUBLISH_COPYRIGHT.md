# GitHub Pages 업데이트 순서

이 ZIP은 `image-toolkit-v60`에 저작권 고지를 추가한 배포용 파일입니다.

## 1. 기존 Git 저장소 폴더로 이동

이미 clone한 저장소가 있다면 해당 `png` 폴더로 이동합니다.

```powershell
cd C:\Users\user\OneDrive\Desktop\압축파일\moonoverlap-png-image-toolkit-v60-publish-root\png
```

없다면 새로 clone합니다.

```powershell
git clone https://github.com/moonoverlap/png.git
cd png
```

## 2. 이 ZIP 안의 파일을 `png` 폴더에 덮어쓰기

중요: `index.html`이 `png` 폴더 바로 안에 있어야 합니다.

## 3. 커밋/푸시

```powershell
git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add .
git commit -m "Add copyright notice"
git push origin main
```
