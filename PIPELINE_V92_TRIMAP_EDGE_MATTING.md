# v9.2 Trimap + Edge Matting Pipeline

이번 버전은 개별 상품 예외를 더하는 방식이 아니라, 로컬 AI 세그멘테이션 결과를 고해상도 알파 매트로 재정제하는 구조입니다.

## 변경 구조

1. Segmentation confidence 추출
   - foreground PNG의 alpha 또는 mask PNG의 luminance를 자동 판정합니다.
2. Adaptive trimap 생성
   - 확정 전경, 확정 배경, unknown boundary band를 분리합니다.
3. Local alpha matting
   - unknown 영역에서 주변 foreground/background seed 색을 샘플링합니다.
   - alpha compositing 공식으로 경계 alpha를 계산합니다.
4. Edge-aware refine
   - 원본 이미지 색상 경계를 따라 알파를 부드럽게 정제합니다.
5. 안정화
   - border-connected low alpha 제거
   - 작은 speckle 제거
   - 작은 pinhole 보정

## 의도

- 패키지/음식/사람/신발 등 개별 예외를 계속 추가하지 않음
- 기본 경로에서는 사각 박스나 상품 보호 마스크를 만들지 않음
- Segmentation은 큰 피사체 영역만 담당
- Matting은 고해상도 경계선과 반투명 영역만 담당
