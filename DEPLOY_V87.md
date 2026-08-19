# Deploy v8.7

```powershell
cd "C:\Users\user\OneDrive\Desktop\압축파일\image-toolkit-v87-natural-food-ai-mode"

if (Test-Path .\_deploy_png) { Remove-Item -Recurse -Force .\_deploy_png }

git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip

cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Add natural food AI-first background removal"
git push origin main
```
