# v7.9 배포 방법

압축 해제한 `image-toolkit-v79-pale-package-lock` 폴더에서 실행합니다.

```powershell
git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip
cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Fix pale package surface holes"
git push origin main
```

확인 주소:

```text
https://moonoverlap.github.io/png/?v=79
```
