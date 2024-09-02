# 8강

## [8.1] Event-Handler

- 어떤 이벤트가 발생했을 때 해당 이벤트를 처리하는 함수
- 이벤트가 발생하는 것을 계속 듣고 있다는 의미로 **_이벤트 리스터_** 라고도 한다
- DOM 이벤트와 다르게 **_카멜표기법_** 이 적용되었다
- DOM에서는 이벤트 처리할 함수를 문자열로 전달하지만 리액트에서는 함수 그래도 전달한다

```jsx
<Button onClick={active}>Active</Button>
```

### 클래스 필드 문법

- 기본적으로 클래스 함수들이 바운드 되지 않기 때문에 **`bind`** 를 사용한다
- bind를 하지 않으면 이벤트 함수가 **_글로벌 스코프에서 호출_** 되고, **`undefined`** 가 되면서 사용할 수 없게 된다
- 이것은 리액트에만 해당되는 내용이 아니라 자바스크립트 함수의 작동 원리 중 일부분이다
- bind를 사용하는 것 대신에 **_클래스 필드 문법을 사용_**
- 이벤트 핸들러를 넣는 곳에 **`arrow function`** 을 사용

```jsx
// 화살표 함수를 사용하는 경우
<Button onClick={() => this.handleClick()}>
	Active
</Button>

// this를 생략하고 사용하는 경우
<Button onClick={handleClick}>
	Active
</Button>
```

## [8.2] Arguments

- 함수에 전달할 데이터를 **`Arguments`** 라고 한다
- 같은 의미로 **`Parameter`** 라는 용어도 많이 사용한다
- **`event`** 는 리액트의 이벤트 객체를 의미한다
