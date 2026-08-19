# v7.8 Corner Hole Repair

흰색 포장지와 흰색 배경이 붙어 있는 상품 이미지에서 모서리 부분이 투명하게 뚫리는 문제를 보정한 버전입니다.

## 핵심 수정

- `buildProductPackageProtectMask()` 추가
- `applyProductProtectAlpha()` 추가
- `sealProductCornerNotches()` 추가
- 닫힌 구멍뿐 아니라 외부와 연결된 열린 모서리 결손까지 보정
- AI 전경 + 색상 연결성 + 상품 패키지 내부 윤곽을 함께 사용

## 배포

```powershell
git clone https://github.com/moonoverlap/png.git _deploy_png
robocopy . .\_deploy_png /E /XD _deploy_png png .git /XF *.zip
cd .\_deploy_png
git config user.name "moonoverlap"
git config user.email "moonoverlap@users.noreply.github.com"
git status
git add -A
git commit -m "Fix product package corner holes"
git push origin main
```
