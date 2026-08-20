# v93 PSD Mask Export

## 변경 사항

- 배경 제거 완료 후 `PSD 마스크 다운로드` 버튼 추가
- 전체 결과를 PSD로 묶는 `PSD 전체 ZIP 다운로드` 버튼 추가
- PSD는 원본 RGB 레이어에 알파 기반 레이어 마스크를 씌우는 구조로 저장
- 자동 크롭/2x/4x 등으로 원본과 결과 크기가 달라진 경우에는 결과 RGB를 기준으로 마스크 PSD 생성
- `ag-psd` 브라우저 번들을 필요할 때만 동적 로드

## 배포

```powershell
cd "C:\Users\user\OneDrive\Desktop\압축파일\image-toolkit-v93-psd-mask-export"

if (Test-Path .\_deploy_png) { Remove-Item -Recurse -Force .\_deploy_png }

git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip

cd .\_deploy_png

git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"

git status
git add -A
git commit -m "Add PSD layer mask export"
git push origin main
```
