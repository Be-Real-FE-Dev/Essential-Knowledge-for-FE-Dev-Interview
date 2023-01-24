# Redux

Redux(리덕스)란 JavaScript(자바스트립트) 상태관리 라이브러리이다.

- 리덕스의 세 가지 원칙
  <br/>
  1. Single source of truth
     - 동일한 데이터는 항상 같은 곳에서 가지고 온다.
     - 스토어라는 하나뿐인 데이터 공간이 있다는 의미이다.
  2. State is read-only
     - 리액트에서는 setState 메소드를 활용해야만 상태 변경이 가능하다.
     - 리덕스에서도 액션이라는 객체를 통해서만 상태를 변경할 수 있다.
  3. Changes are made with pure functions
     - 변경은 순수함수로만 가능하다.
     - 리듀서와 연관되는 개념이다.
     - Store(스토어) – Action(액션) – Reducer(리듀서)

<br>

## Flux 패턴

사용자 입력을 기반으로 Action을 만들고 Action을 Dispatcher에 전달하여 Store(Model)의 데이터를 변경한 뒤 View에 반영하는 **단방향의 흐름**으로 애플리케이션을 만드는 아키텍처

- Action
  - 데이터를 변경하는 행위로서 Dispatcher에게 전달되는 객체
  - Action의 타입(type)과 새로운 데이터(payload)를 묶어 Dispatcher에게 전달
- Dispatcher
  - 모든 데이터의 흐름을 관리하는 중앙 허브
  - Action을 감지하면 Store들이 각 타입에 맞는 Store의 콜백 함수를 실행
  - Store의 데이터를 조작하는 것은 오직 Dispatcher를 통해서만 가능
- Model(Store)
  - 상태 저장소로서 상태와 상태를 변경할 수 있는 메서드를 가짐
  - 어떤 타입의 Action이 발생했는지에 따라 그에 맞는 데이터 변경을 수행하는 콜백 함수를 Dispatcher에 등록
  - Dispatcher에서 콜백 함수를 실행하여 상태가 변경되면 View에게 데이터가 변경되었음을 알림
- View : 컴포넌트

![image](https://user-images.githubusercontent.com/92196967/214202046-0bc2489e-05a9-4713-b4de-594bd04b2190.png)

<br/>

## Redux에서 불변성을 유지해야하는 이유

내부적으로 데이터가 변경 되는 것을 감지하기 위하여 shallow equality 검사를 하기 때문. 이를 통하여 객체의 변화를 감지 할 때 객체의 깊숙한 안쪽까지 비교를 하는 것이 아니라 겉핥기 식으로 비교를 하여 좋은 성능을 유지할 수 있는 것

<br>

## 장단점

- 장점

  - 단방향 모델링
  - 상태를 한 곳에서 관리(중앙화)

- 단점
  - 작은 기능을 리덕스로 구현해도 필수로 작성해야하는 코드량이 많음
  - 상태를 읽기 전용으로 취급할 뿐, 실제 읽기 전용으로 만들지는 않음<br>
    🚨 직접 변경하지 않도록 항상 주의. 예방하기 위해 immutable.js같은 라이브러리 존재.

<br>

> 참고 출처 <br> > https://hanamon.kr/redux%EB%9E%80-%EB%A6%AC%EB%8D%95%EC%8A%A4-%EC%83%81%ED%83%9C-%EA%B4%80%EB%A6%AC-%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC/ > https://velog.io/@andy0011/Flux-%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80
