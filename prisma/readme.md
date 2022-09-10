# 데이터 베이스 가이드

# ToC

- 프로젝트 스키마
- 스키마 상세 구성
  - Bander
  - Device
  - Contract
  - Product
  - Benefit

## 프로젝트 스키마

프로젝트 ERD

<Center>
<img src="https://user-images.githubusercontent.com/55491354/189496392-386e47c1-bbea-4730-b7f8-09cbc01e7ecf.png" height="300px" title="ERD"/>
</Center>

## 스키마 상세 구성

각 테이블에 대한 정보 비즈니스 로직에 대한 개요를 작성합니다

### `Bander` 통신 사업자

- `name` 통신사업자 명

### `Device` 단말기 정보

- `name` 단말기 명
- `price` 단말기 출고가

### `Contract` 요금제 정보

- `bandType` 통신기술 분류 (LTE, 5G)
- `name` 요금제 명
- `voice` 음성 제공량 (분)
- `sms` 문자메시지 제공량 (건)
- `defaultData` 기본 데이터 제공량 (MB)
- `qosData` 모든데이터 사용 시 속도 제한 (mBps)(NULL = 과금)(0 = 데이터 제공 중지)
- `everyData` 매일 데이터 제공량 (MB)(0=없음)

### `Product` 상품 정보

Contract(요금제)는 다양한 Bander(통신 사업자)가 다양한 Benefit(혜택)을 주며 판매할 수 있습니다

- `isMvno` MVNO 자급제 상품 유무
- `name` 상품 명
- `joinCondition` 가입 조건 (NAC-신규, MNP-번이, HCN-기변)
- `price` 제품 가격

### `Benefit` 상품 할인 정보

Product(상품)은 여러 Benefit(혜택)을 가질 수 있습니다

- `type` 혜택 유형 (할인, 쿠폰)
- `name` 혜택 명
- `price` 혜택 가치 (원)
- `cycleType` 혜택 지급 주기 (일, 월)
- `cycle` 혜택 실행 주기 (cycleType:일 이고 cycle:3일 시 3일마다 혜택 지급)
- `count` 혜택 지급 횟수 (몇 회 혜택을 주는지)
