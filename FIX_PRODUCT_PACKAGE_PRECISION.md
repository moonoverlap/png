# v7.2 정밀 상품 패키지 누끼 수정

## 문제

흰 배경 위에 흰색 포장지/흰 라벨이 있는 상품 이미지에서, 배경 제거 로직이 제품 내부의 흰색 영역까지 배경으로 오인해 투명 처리하는 문제가 있었습니다.

## 수정 방향

Photoroom의 독점 기술을 복제하지 않고, 같은 목적의 상품 패키지용 정밀 피사체 인식 흐름을 추가했습니다.

- 로고, 텍스트, 식품 사진, 컬러 인쇄, HACCP 마크, 파란/빨간 포장 영역을 피사체 기준점으로 먼저 감지
- 기준점의 행/열 범위를 보간해 제품 외곽 envelope 생성
- envelope 안쪽의 흰색/밝은 회색 포장지와 라벨은 피사체로 보호
- envelope 바깥의 흰 배경만 투명 처리

## 기본값

제거 방식 기본값을 다음으로 변경했습니다.

```text
상품 패키지 정밀 · 흰 포장/라벨 보호
```

## Git 반영

```powershell
git status
git add .
git commit -m "Improve product package background removal"
git push origin main
```
