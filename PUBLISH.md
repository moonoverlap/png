# moonoverlap.github.io/png 업데이트용

이 ZIP은 사용자가 업로드한 `image-toolkit-v60.zip`을 기준으로 다시 만든 GitHub Pages 루트 업로드용 파일입니다.

## 현재 상황

기존에 `git clone`을 해서 아래 폴더가 생긴 상태라면:

```powershell
C:\Users\user\OneDrive\Desktop\압축파일\moonoverlap-png-v44-publish-root\png
```

이 ZIP을 압축 해제한 뒤, 압축 해제된 파일들을 위 `png` 폴더 안에 덮어쓰면 됩니다.

## PowerShell 명령

`png` 폴더 안에서 실행:

```powershell
git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

Copy-Item ..\image-toolkit-v60-publish\* .\ -Recurse -Force

git status
git add .
git commit -m "Update image toolkit v60"
git push origin main
```

## 주의

- `index.html`이 GitHub 저장소 루트에 있어야 합니다.
- 하위 폴더째 올라가면 `https://moonoverlap.github.io/png/`에 반영되지 않습니다.
- commit이 성공해야 push할 내용이 생깁니다.
