---
title: 왼쪽 시프트 (<<)
slug: Web/JavaScript/Reference/Operators/Left_shift
---

{{jsSidebar("Operators")}}

**왼쪽 시프트 (`<<`)** 연산자는 첫 번째 피연산자를 명시된 비트 수(32의 나머지)만큼 왼쪽으로 이동합니다. 왼쪽으로 이동된 초과 비트는 폐기됩니다. 오른쪽은 움직인 비트 수 만큼 0비트로 채워집니다.

{{InteractiveExample("JavaScript Demo: Expressions - Left shift operator", "shorter")}}

```js interactive-example
const a = 5; // 00000000000000000000000000000101
const b = 2; // 00000000000000000000000000000010

console.log(a << b); // 00000000000000000000000000010100
// Expected output: 20
```

## 구문

```js-nolint
a << b
```

## 설명

이 연산자는 첫 번째 피연산자를 명시한 비트 수만큼 왼쪽으로 이동합니다. 왼쪽으로 이동된 초과 비트는 폐기됩니다. 오른쪽은 움직인 비트 수 만큼 0 비트로 채워집니다.

예를 들어, `9 << 2`은 36이 도출됩니다.

```
     9 (10진수): 00000000000000000000000000001001 (2진수)
                  --------------------------------
9 << 2 (10진수): 00000000000000000000000000100100 (2진수) = 36 (10진수)
```

임의의 숫자 `x`를 왼쪽으로 `y`비트 단위로 이동하면 `x * 2 ** y`입니다. 그래서 예를 들어
`9 << 3`은 `9 * (2 ** 3) = 9 * (8) = 72`으로 해석됩니다.

왼쪽 피연산자는 32비트 정수로 변환됩니다. 즉, 부동 소수점 숫자는 잘리고 32비트 경계 내에 있지 않은 숫자는 오버플로우/언더플로우됩니다.

오른쪽 피연산자는 부호 없는 32비트 정수로 변환된 다음 32 나머지 연산의 값을 가져오므로 실제 시프트 오프셋은 항상 0에서 31 사이의
양의 정수입니다. 예를 들어, `100 << 32`는 `100 << 0`과 동일(이 결과값은 `100`입니다)합니다. 32 나머지 연산은
0이기 때문입니다.

## 예제

### 왼쪽 시프트 사용하기

```js
9 << 3; // 72
// 9 * (2 ** 3) = 9 * (8) = 72
```

## 명세서

{{Specifications}}

## 브라우저 호환성

{{Compat}}

## 같이 보기

- [JavaScript에서 비트 연산자 가이드](/ko/docs/Web/JavaScript/Guide/Expressions_and_operators#%eb%b9%84%ed%8a%b8_%ec%97%b0%ec%82%b0%ec%9e%90)
- [왼쪽 시프트 할당 연산자](/ko/docs/Web/JavaScript/Reference/Operators/Left_shift_assignment)
