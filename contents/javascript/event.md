# event

## 예상 질문

- 리액트의 이벤트 위임

- 이벤트루프

## 이벤트 캡처링

이벤트가 발생한 하위 요소에서 상위요소가 이벤트가 전달되는 방식 \*인라인 방식은 캡처링을 쓸 수 없다.
why? addEventListener만 3번째 인수로 capture 방식 설정 가능.

## 이벤트 버블링

상위 요소에서 이벤트가 발생한 하위요소로 이벤트가 전달되는 방식

## 이벤트 위임

상위 요소에 이벤트 핸들러를 달아 하위 요소를 제어. 메모리에 있게 되는 이벤트 핸들러가 적어져 퍼포먼스 측면에서 이점.

## 참고

- [React event 위임1](https://blog.mathpresso.com/react-deep-dive-react-event-system-1-759523d90341)
- [React event 위임2](https://blog.mathpresso.com/react-deep-dive-react-event-system-2-1d0ad028308b)
- [이벤트 루프](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
