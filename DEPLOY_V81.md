# v81 배포 안내

```powershell
cd "C:\Users\user\OneDrive\Desktop\압축파일\image-toolkit-v81-outer-white-trim"

if (Test-Path .\_deploy_png) { Remove-Item -Recurse -Force .\_deploy_png }

git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip
cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Trim outer white background residue"
git push origin main
```

확인 주소:

```text
https://moonoverlap.github.io/png/?v=81
```
