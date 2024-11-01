# 💰 로또 발매기 💰

이 프로젝트는 간단한 **로또 발매기**를 구현한 것입니다. 사용자는 원하는 금액의 *로또*를 구매할 수 있으며, 구매한 로또 번호와 당첨 번호를 비교하여 당첨 내역 및 수익률을 출력합니다.

## 🎯 기능 설명

- [x] 사용자가 로또 구입 금액을 입력하면 구입 금액에 해당하는 만큼 로또를 발행합니다.
  - [x] 구입 금액은 1,000원 단위로 입력 받으며 1,000원으로 나누어 떨어지지 않는 경우 예외로 처리됩니다.
- [ ] 사용자로부터 당첨 번호와 보너스 번호를 입력받습니다.
  - [x] 로또 번호의 숫자 범위는 1~45까지 입니다.
  - [x] 번호는 쉼표(,)를 기준으로 구분합니다.
  - [x] 1개의 로또를 발행할 때 중복되지 않는 6개의 숫자를 뽑습니다.
  - [x] 당첨 번호 추첨 시 중복되지 않는 숫자 6개와 보너스 번호 1개를 뽑습니다.
- [x] 당첨은 1등부터 5등까지 있으며, 당첨 기준과 금액은 아래와 같습니다.
    1등: 6개 번호 일치 / 2,000,000,000원
    2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
    3등: 5개 번호 일치 / 1,500,000원
    4등: 4개 번호 일치 / 50,000원
    5등: 3개 번호 일치 / 5,000원
- [x] 발행한 로또 수량 및 번호를 출력합니다.
  -[x] 로또 번호는 오름차순으로 정렬하여 출력합니다.
- [x] 사용자가 구매한 로또 번호와 당첨 번호를 비교하여 당첨 내역 및 수익률을 출력하고 로또 게임을 종료합니다.
  -[x] 수익률은 소수점 둘째 자리에서 반올림하여 출력합니다.
- [x] 사용자가 잘못된 값을 입력할 경우 "[ERROR]"로 시작하는 메시지와 함께 Error를 발생시키고 해당 메시지를 출력한 다음 해당 지점부터 다시 입력을 받습니다.



## ❓예상 ERROR 상황 목록

- 로또 금액 입력 부분

  - [x] 숫자가 아닌 값을 입력했을 경우
    - [x] 에러를 반환(`[ERROR] 잘못된 입력입니다. 숫자를 입력해 주세요.`)
  - [x] 0이 입력된 경우
    - [x] 에러를 반환(`[ERROR] 0원이 입력되었습니다. 1개 이상의 로또를 구매해 주세요.`)
  - [x] 1000으로 나누어 떨어지지 않는 경우
    - [x] 에러를 반환(`[ERROR] 로또 1개의 가격은 1000원입니다. 1000원 단위로 입력해 주세요.`)
  - [x] 금액이 10만원을 초과할 경우
    - [x] 에러를 반환(`[ERROR] 로또는 1회 10만원까지만 구매 가능합니다.`)

- 로또 번호 입력 부분

  - [x] 숫자가 아닌 값을 입력했을 경우
    - [x] 에러를 반환(`[ERROR] 잘못된 입력입니다. 숫자를 입력해 주세요.`)
  - [x] 1~45 외의 숫자를 입력했을 경우
    - [x] 에러를 반환(`[ERROR] 가능한 번호는 1~45입니다. 올바른 번호를 입력해주세요.`)
  - [ ] **당첨 번호 입력 부분**에서 6개가 아닌 숫자를 입력했을 경우
    - [x] 에러를 반환(`[ERROR] 당첨 번호는 6개이나, x개의 번호를 입력하셨습니다. 다시 입력해주세요.`)
  - [x] 6개의 숫자 중 중복되는 숫자가 있을 경우
    - [x] 에러를 반환(`[ERROR] 6개의 번호 중 중복되는 번호가 있습니다. 다시 입력해주세요.`)
  - [ ] **보너스 번호 입력 부분**에서 1개가 아닌 숫자를 입력했을 경우
    - [x] 1개 이상의 번호가 입력된 경우 (쉼표(,)가 포함된 경우)
      - [x] 에러를 반환(`[ERROR] 보너스 번호는 1개입니다. 다시 입력해주세요.`)
    - [x] 번호가 입력되지 않은 경우 
      - [x] 에러를 반환(`[ERROR] 번호가 입력되지 않았습니다. 1개의 번호를 입력해주세요.`)

## ⭐ 입출력 요구 사항

### 입력

1. **구매할 로또 금액** (숫자 입력)
   - 예시: `8000`
2. **당첨 번호** (6개의 숫자 입력. 번호는 쉼표(,)로 구분)
   - 예시: `1,2,3,4,5,6`
3. **보너스 번호** (숫자 하나 입력)
   - 예시: `7`

### 출력

**로또 발행 결과**

발행한 로또 수량 및 번호를 출력합니다. 로또 번호는 오름차순으로 정렬합니다.

```
8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]
```

**당첨 내역**

```
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
```
  
**수익률**

수익률은 소수점 둘째 자리에서 반올림하여 출력합니다. (ex. 100.0%, 51.5%, 1,000,000.0%)
```
총 수익률은 62.5%입니다.
```

### 실행 예시

```
구입금액을 입력해 주세요.
8000

8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

당첨 번호를 입력해 주세요.
1,2,3,4,5,6

보너스 번호를 입력해 주세요.
7

당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```