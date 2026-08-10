# 일본 중고 카메라 마켓 — 크로스샵 가격 비교 (Kitamura + Fujiya)

**일본 최대 중고 카메라 체인 키타무라(全国 300+ 매장)와 일본 최고령 중고 카메라 전문점 후지야 카메라의 횡적 가격 비교.** 동일 카메라 모델의 매장별 가격 차이를 한눈에 확인할 수 있어, 직구·되팔기·시세 조사에 최적입니다.

> 🇯🇵 English/日本語版: [Japan Used Camera Market](https://apify.com/fruitful_quintessence/japan-used-camera-market-scraper)

## 왜 유용한가

- **크로스샵 비교**: 키타무라(일본 최대 중고 카메라 체인)와 후지야 카메라(1956년 창업 중고 카메라 전문점)를 동시 검색
- **실제 재고**: 각 매장의 실제 재고 상태 표시, '이 매장은 품절 저 매장은 재고'를 빠르게 발견
- **엔화 가격**: 엔화 기준 가격 직접 출력, 직구/되팔기 마진 계산에 편리
- **프록시 불필요**: 키타무라 직결 API, 빠르고 안정적

## 입력

| 필드 | 타입 | 기본값 | 설명 |
|---|---|---|---|
| `searchKeyword` | string | `α7` | 카메라/렌즈 이름 (비우면 전체 카테고리 스캔) |
| `maxItems` | integer | 100 | 최대 수집 개수 |
| `maxPages` | integer | 2 | 소스별 최대 페이지 수 |
| `sources` | string | `kitamura,fujiya` | 소스 (쉼표 구분) |

## 출력 필드

| 필드 | 설명 |
|---|---|
| `productId` | 상품 ID |
| `title` | 상품명 |
| `price` | 가격 (엔화) |
| `brand` | 브랜드 |
| `shop` | 매장명 |
| `category` | 카테고리 |
| `condition` | 상태 (신품/미사용/중고 등) |
| `stockStatus` | 재고 상태 |
| `imageUrl` | 이미지 URL |
| `productUrl` | 상품 링크 |
| `source` | `kitamura` or `fujiya` |
| `scrapedAt` | 수집 시각 |

## 출력 예시

```json
{
  "productId": "253468",
  "title": "소니 α7III",
  "brand": "SONY",
  "price": 130600,
  "shop": "키타무라 넷 중고",
  "condition": "중고품A",
  "stockStatus": "재고 있음",
  "source": "kitamura",
  "productUrl": "https://shop.kitamura.jp/ec/prd/253468",
  "scrapedAt": "2026-08-10T10:00:00Z"
}
```

## 활용 시나리오

- **직구/되팔기**: 저가 중고 카메라 발견 → 마진 확보
- **시세 조사**: 특정 모델의 시장 가격 추이 추적
- **재고 모니터링**: 300+ 매장의 재고 변화 감시

## 가격

이벤트당 과금 — $0.00005/실행 + **$0.002/건**.

## 데이터 출처

키타무라 공개 검색 API + 후지야 카메라 검색 페이지. 공개 상품 정보(명칭, 가격, 브랜드, 재고 상태)만 수집합니다.
