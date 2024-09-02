# 9장 Condtional Rendering

## Condtional Rendering이란?

Condtion 즉 조건에 따라 렌더링이 달라 지는 것으로 조건문의 결과가 true인지 false인지에 따라 렌더링을 다르게 하는것을 의미한다.

<img src=".\Image\1.png">

<img src=".\Image\2.png">

(if문의 조건에 따라 다른 컴포넌트가 렌더링 되는 모습)

## Truthy와 Falsy

Thruty와 Falsy는 자바스크립트에서 기존에 true와 false로 변환되는 값 외에 암묵적으로 변환되는 값을 의미한다.

### Truthy

- true
- { } (empty object)
- [ ] (empty array)
- 11 (0이 아닌 숫자)
- “0”, “false” (문자열)

### Falsy

- false
- 0, -0
- 0n (BigInt zero)
- ‘’, “”, `` (빈 문자열)
- null
- undefined
- NaN(not a number)

## Element Variables

리액트의 엘리먼트를 변수처럼 다루는 방법

<img src=".\Image\3.png">

<img src=".\Image\4.png">

Login과 Logout 컴포넌트로 부터 생성된 리액트 엘리먼트를 조건에 따라 button이라는 변수에 할당하는 모습이다.

## Inlince Conditions

Inline Conditions는 조건문을 코드 안에 집어 넣는 방법으로 코드를 좀 더 간결하게 만들 수 있으며

Inline if와 Inline if-else 두가지 방법이 있다.

### Inline if

Inline if는 &&(and) 연산을 활용해서 이루어진다.

&&(and)연산은 두 가지 조건이 모두 true가 되어야 true를 출력하는 연산으로 (A && B)인 경우

먼저 A연산의 결과를 보고 true이면 B연산의 결과를 확인하고 A가 false인 경우 B연산을 확인하지 않고 false를 반환한다. 이를 단축 평가(Short-Circuit)라 한다.

### 주의점

<img src=".\Image\5.png">

이런 경우 count값이 0이기 때문에 falsy로 뒤에 “<h1>현재 카운트: {count}</h1>”는 실행되지 않으며 “<div>0</div>”과 같은 원치 않는 값이 리턴된다.

### Inline if-else

Inline if-else는 삼항 연산자를 통해 표현하며 true경우와 false일 경우에 따라 다른 항목을 리턴할 수 있게 해준다.

<img src=".\Image\6.png">

만약 결과가 true일 경우 “로그인”이 반환되고 false인 경우 “로그인하지 않은”이 반환된다.

## Component 랜더링 막기

사용자가 원할 때만 렌더링 하는 방법은 렌더링을 원치 않을 때 null 값을 반환하면 된다.
null 값을 반환하는 것은 컴포넌트의 생명주기 함수에 영향을 끼치지 않는다.
