# Virtual DOM

Virtual DOM은 실제 DOM과 동기화 된 객체이다.
react에서 render함수가 실행되고 reconcillation 작업을 거쳐 실제 DOM을 표현하게 된다.

react에서 상태가 변경되면 virtual dom이 갱신된다. 그런 다음 이전 virtual DOM과 새로운 virtual DOM을 비교하고 변경 사항을 실제 DOM요소에서 업데이트 된다.

> Virtual DOM (VDOM)은 UI의 이상적인 또는 “가상”적인 표현을 메모리에 저장하고 ReactDOM과 같은 라이브러리에 의해 “실제” DOM과 동기화하는 프로그래밍 개념

이 접근방식이 React의 선언적 API를 가능하게 합니다. React에게 원하는 UI의 상태를 알려주면 DOM이 그 상태와 일치하도록 합니다. 이러한 방식은 앱 구축에 사용해야 하는 어트리뷰트 조작, 이벤트 처리, 수동 DOM 업데이트를 추상화합니다.

실제 DOM에서 처리하는 방식이 아닌 Virtual DOM과 메모리에서 미리 처리하고 저장한 후 실제 DOM과 동기화하는 프로그래밍 개념이다. DOM을 컴포넌트 단위로 쪼개어 HTML 컴포넌트 조립품처럼 다루는 개념.

<br>
실제 DOM에는 브라우저가 화면을 그리는 데 필요한 모든 정보를 담고 있기 때문에 실제 DOM을 조작하는 작업은 무겁기 때문에 virtual DOM을 만들어서 관리한다.

<br>
- 원리
  - 각 컴포넌트가 반환하는 엘리먼트를 이전에 반환했던 엘리먼트와 비교하여(reconcilation) 다른 부분이 있다면 해당 DOM Node에 CRUD 작업 수행.
- DOM 조작에 의한 렌더링의 비효율적인 문제 해결
- SPA 특징으로 DOM 복잡도 증가에 따른 최적화 및 유지 보수의 어려움 해결.
