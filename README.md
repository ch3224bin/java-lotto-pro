# 로또
## 진행 방법
* 로또 요구사항을 파악한다.
* 요구사항에 대한 구현을 완료한 후 자신의 github 아이디에 해당하는 브랜치에 Pull Request(이하 PR)를 통해 코드 리뷰 요청을 한다.
* 코드 리뷰 피드백에 대한 개선 작업을 하고 다시 PUSH한다.
* 모든 피드백을 완료하면 다음 단계를 도전하고 앞의 과정을 반복한다.

## 온라인 코드 리뷰 과정
* [텍스트와 이미지로 살펴보는 온라인 코드 리뷰 과정](https://github.com/next-step/nextstep-docs/tree/master/codereview)

## 문자열 덧셈 계산기

### 기능 요구사항

- [x] 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환 (예: “” => 0, "1,2" => 3, "1,2,3" => 6, “1,2:3” => 6)
- [x] 앞의 기본 구분자(쉼표, 콜론)외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 “//”와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다. 예를 들어 “//;\n1;2;3”과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- [x] 문자열 계산기에 숫자 이외의 값 또는 음수를 전달하는 경우 RuntimeException 예외를 throw한다.

### 사용방법

```java
int result = StringAddCalculator.splitAndSum("//;\n1;2;3");
System.out.println(result); // print 6
```
## 로또 (자동)

### 기능 요구사항

- 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
- 로또 1장의 가격은 1000원이다.

### 출력 결과

```text
구입금액을 입력해 주세요.
14000
14개를 구매했습니다.
[8, 21, 23, 41, 42, 43]
[3, 5, 11, 16, 32, 38]
[7, 11, 16, 35, 36, 44]
[1, 8, 11, 31, 41, 42]
[13, 14, 16, 38, 42, 45]
[7, 11, 30, 40, 42, 43]
[2, 13, 22, 32, 38, 45]
[23, 25, 33, 36, 39, 41]
[1, 3, 5, 14, 22, 45]
[5, 9, 38, 41, 43, 44]
[2, 8, 9, 18, 19, 21]
[13, 14, 18, 21, 23, 35]
[17, 21, 29, 37, 42, 45]
[3, 8, 27, 30, 35, 44]

지난 주 당첨 번호를 입력해 주세요.
1, 2, 3, 4, 5, 6

당첨 통계
---------
3개 일치 (5000원)- 1개
4개 일치 (50000원)- 0개
5개 일치 (1500000원)- 0개
6개 일치 (2000000000원)- 0개
총 수익률은 0.35입니다.(기준이 1이기 때문에 결과적으로 손해라는 의미임)
```

### 기능 목록

- [X] 로또 번호 생성기
  - [X] 1에서 45 사이의 겹치지 않는 숫자를 6개를 생성한다
  - [X] 6개의 각 숫자는 1/45에 근접한 확률로 생성된다
- [X] 금액 입력 로직
  - [X] 1000으로 나누어지는 금액을 입력 받는다
  - [X] 입력 받은 금액을 1000으로 나눈 결과를 반환한다
- [X] 구입 금액 만큼 로또 번호 생성
  - [X] 구입 숫자 만큼 로또 번호를 출력한다
- [X] 당첨 번호 입력
  - [X]  ','로 나누었을 때 6개의 숫자로 나뉘는 문자열을 입력받는다
  - [X] 나뉘어진 숫자는 1에서 45사이다
  - [X] 나뉘어진 숫자는 서로 겹치지 않는다
- [X] 당첨번호와 로또 번호 비교
  - [X] 당첨번호와 로또 번호에서 일치하는 숫자의 개수를 반환한다
- [X] 당첨 통계
  - [X] 3개가 일치하면 5000 원을 받는다
  - [X] 4개가 일치하면 50,000 원을 받는다
  - [X] 5개가 일치하면 1,500,000 원을 받는다
  - [X] 6개가 일치하면 2,000,000,000 원을 받는다
  - [X] 각 당첨 금액별 합계를 낸다
  - [X] 구입비용 대 당첨금액의 수익률을 계산한다 (수익률 = 당첨금액 / 수입금액)
- [ ] 게임 진행
  - [ ] 구입금액을 입력 받는다
  - [ ] 구입받은 금액으로 몇 개의 로또를 샀는지 출력한다
  - [ ] 구매한 로또 번호를 출력한다
  - [ ] 지난주 당첨 번호를 입력 받는다
  - [ ] 당첨 통계를 출력한다
