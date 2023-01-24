# Context API

context api를 이용하면 단계마다 일일이 props를 넘겨주지 않고도 컴포넌트 트리 전체에 데이터를 제공할 수 있습니다.

-> props drilling을 해결할 수 있다.

- Context API는 종속성을 주입하기위한 도구일 뿐이다. React에서의 실질적인 상태관리는 useState, useReducer를 통해 일어난다.

<br>

## Context API 장점과 단점

- 장점 : props drilling을 해결할 수 있다.
- 단점 : Provider의 value prop에 있는 state와 dispatch가 변할 때 마다, Provider를 구독하고 있는 모든 컴포넌트들이 리렌더링이 된다.
  Context가 많아지면 Provider Hell이 발생한다.
