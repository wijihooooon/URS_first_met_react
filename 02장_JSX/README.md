## 1.1 JSX란 무엇일까?

JSX ( Javascript Syntax Extension ) 는 Javascript 확장 문법이다. 리액트로 프로젝트를 개발할 때 사용되므로 공식적인 JS 문법은 아니다. 그럼 JSX를 어떻게 사용할 수 있는 걸까?? 정답은 브라우저에서 실행 전에 바벨을 사용하여 일반 자바스크립트 형태의 코드로 변환되는 과정을 거치기 때문이다.

```jsx
const element = <div>Hello, World!</div>;
```

우리가 일반적으로 알고있던 코드의 작성법과 뭔가 다르다. 변수 안에 HTML 태그를 저장할 수 있고 이를 활용하여 더욱 작고 모던한 컴포넌트 들을 개발하며 작업의 편리성을 올려주게  된다.

```jsx
// JSX
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>);

// JS로 변환된 JSX
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

기본적으로 리액트를 처음 실행하는 방법에 대해 생각해 본적이 있나 싶다. 리액트는 분명 하나의 언어가 아닌 라이브러리 이자 프레임워크 의 개념인데, 어떻게 브라우저 상에 JS 코드와 똑같이 작동하는 걸까?

```jsx
// main.jsx

import ReactDOM from 'react-dom/client';
import App from './App.jsx';
import './index.css';

ReactDOM.createRoot(document.getElementById('root')).render(
    <App />
);
```

```html
<!-- index.html -->
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
    <script>
      const global = globalThis;
    </script>
  </body>
</html>

```

> 예재 코드블럭을 보며 이해를 시작해보면 된다. 처음 리액트 프로젝트를 실행하면 npm run start 나 npm run dev 라는 명령어를 접하게 된다. 해당 명령어가 정상적으로 실행이 되면 브라우저는 기본 라우터인 index.html 을 실행하게 된다.
>

> 예를 들어 현재 리액트 프로젝트의 포트가 3000 번 포트라고 하면, [`localhost:3000/`](http://localhost:3000/) 으로 접속을 하면 react 가 켜진 3000번 포트의 / 주소로 접속을 하게 되는 것이다. 그럼 / 주소는 프로젝트의 기본 주소인 `index.html` 이므로 해당 파일로 이동을 하게된다. 자 여기서 힌트가 생긴다 body 태그에 잘 보면
>

```jsx
<body>
    <div id="root"></div> 
    <script type="module" src="/src/main.jsx"></script>
    <script>
      const global = globalThis;
    </script>
  </body>
```

- div id = “root” 라는 문구를 통해 div 의 id가 root 인 div이 그려져있다는것을 알 수 있다.

아래에는 script 태그가 있는데 module 로 main.jsx 라는 파일을 불러오겠다는 뜻이다. 그러면 다시 main.jsx 로 돌아가보자.  `ReactDOM.createRoot(document.getElementById('root')).render(<App/>);`

라는 문법이 보인다. root 라는 아이디의 dom 을 찾아서 해당 위치에 React만의 문법인 createRoot 를 통해 어원 그대로 뿌리를 만든다, 리액트 파일을 여기서 시작하겠다 라는 의미이다. 실제로 React 프로젝트 파일들의 dom 트리 구조를 보면 div id가 root 인 태그 아래에서 모든 프로젝트가 빌드가 되는것을 알 수 있다.

결국 JSX 를 사용하면서 얻을 수 있는 장점에는 코드가 한결 간결해지는 것, 이로 인한 가독성 향상 등을 기대할 수 있고, 기본적으로는 JS 와 똑같으니 나머지 예재들은 추후에 다뤄보면 된다.