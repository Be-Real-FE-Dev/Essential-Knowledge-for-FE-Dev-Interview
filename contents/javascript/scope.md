# Scope

## 예상 질문

- var, const, let의 차이점.
  | |var|let|const|
  |---|---|---|-----|
  |origin|pre ES2015|ES6|ES6|
  |scope| globally scope or function scoped. atteached to window object| globally scoped or block scoped | globally scoped or block scope|
  |hoisting|undefined| TDZ |TDZ|
  |redeclaration|yes|no|no|
  |reassigned|yes|yes|no|

- 전역 scope를 사용했을 때 장단점.
  장점: 최상위 스코프이기 때문에 쉽게 모두 접근할 수 있다.
  단점:
  메모리적 단점: 전역 변수는 애플리케이션 사용동안 사라지지 않는다(가비지 컬렉팅 타겟이 아니다).
  유지보수적 단점: 식별자가 중첩될 경우, 가독성과 신뢰성이 떨어짐
  객체지향적 단점: 캡슐화, 은닉화를 할 수 없다.

- 스코프 체인: 실행컨텍스트 상에 OuterLexicalEnvironment Reference의 참조값의 연결

## 참조 사항

[전역변수 가비지 컬렉션](https://ko.javascript.info/garbage-collection)

- 가비지 컬렉션 기준
  자바스크립트는 도달 가능성(reachability) 이라는 개념을 사용해 메모리 관리를 수행합니다.

‘도달 가능한(reachable)’ 값은 쉽게 말해 어떻게든 접근하거나 사용할 수 있는 값을 의미합니다. 도달 가능한 값은 메모리에서 삭제되지 않습니다.

아래 소개해 드릴값들은 그 태생부터 도달 가능하기 때문에, 명백한 이유 없이는 삭제되지 않습니다.

예시:
현재 함수의 지역 변수와 매개변수
중첩 함수의 체인에 있는 함수에서 사용되는 변수와 매개변수
전역 변수
기타 등등
이런 값은 루트(root) 라고 부릅니다.
<br/>
[GC](https://ko.javascript.info/garbage-collection);
