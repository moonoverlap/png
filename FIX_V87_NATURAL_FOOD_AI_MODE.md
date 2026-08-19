# v8.7 Natural Food / Dish Photo AI-first Mode

## 문제 원인

명란/접시 사진은 상품 패키지 이미지가 아니라 일반 푸드 사진입니다. 기존 v78~v86은 흰 포장지와 라벨을 보호하기 위해 `colorAlpha`와 상품 패키지 보호 마스크를 AI 결과에 합쳤습니다.

이 방식은 피자/육포/해물경단 같은 흰 패키지에는 도움이 되지만, 회색 테이블 배경이 있는 음식 사진에서는 배경까지 전경으로 살아나는 문제가 있었습니다.

## 수정

- `looksLikeNaturalFoodOrDishPhoto()` 추가
- `refineNaturalPhotoForegroundAlpha()` 추가
- 일반 푸드/접시 사진은 패키지 보호 마스크를 건너뛰고 AI 마스크 우선 사용
- `background_only` 빠른 모드에서도 회색/베이지 테이블 배경 사진은 AI 모드로 자동 전환
- 기본 모델을 `isnet` 고품질로 변경

## 처리 원칙

- 네모 인쇄 패키지: 패키지 보호 로직 사용
- 투명 비닐/소프트팩: AI 우선 + 제한 보정
- 일반 푸드/접시 사진: AI 마스크만 사용
