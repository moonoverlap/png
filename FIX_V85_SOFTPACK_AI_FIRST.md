# v8.5 Soft-pack AI-first fix

## 원인

v83/v84는 네모 패키지와 비정형 상품을 나눴지만, AI 결과 위에 `buildPalePackageSurfaceProtectMask`, `buildTestedProductEnvelopeProtectMask`, `trimOutsideStructuralProductEnvelope`, `applyCatalogPackageBoxLock` 같은 넓은 보호/잠금 로직이 계속 적용되었습니다.

크래미 1kg처럼 투명 비닐/진공팩/흰 내용물이 섞인 상품은 이 보호 로직이 실제 상품 외곽이 아니라 흰 배경 카드까지 전경으로 보존했습니다.

## 수정

- `looksLikeSoftTransparentPackage()` 추가
- 투명 비닐/진공팩/비정형 소프트팩은 넓은 보호 마스크와 박스 잠금을 건너뜀
- 해당 유형은 AI 마스크를 우선 사용
- 색상 보정은 강한 인쇄, 식품, 비닐 주름/엣지에만 제한
- `trimEdgeConnectedCanvasWhite()`로 바깥과 연결된 실제 캔버스 흰 배경만 제거

## 핵심

사각 박스 기준 보정은 네모 인쇄 패키지에만 사용하고, 투명 비닐/진공팩에는 사용하지 않습니다.
