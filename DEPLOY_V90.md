# v90 배포 방법

압축을 푼 폴더에서 실행합니다.

```powershell
cd "C:\Users\user\OneDrive\Desktop\압축파일\image-toolkit-v90-local-segmentation-matting"

if (Test-Path .\_deploy_png) { Remove-Item -Recurse -Force .\_deploy_png }

git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip

cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Redesign local segmentation matting pipeline"
git push origin main
```

확인 주소:

```text
https://moonoverlap.github.io/png/?v=90
```
