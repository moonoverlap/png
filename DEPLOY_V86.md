# v86 배포

```powershell
cd "C:\Users\user\OneDrive\Desktop\압축파일\image-toolkit-v86-no-artificial-outline"

if (Test-Path .\_deploy_png) { Remove-Item -Recurse -Force .\_deploy_png }

git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip

cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Remove artificial outline from subject protection"
git push origin main
```

확인: https://moonoverlap.github.io/png/?v=86
