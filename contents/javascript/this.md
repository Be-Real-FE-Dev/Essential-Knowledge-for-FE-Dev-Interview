# this 바인딩

- .call과 .apply의 차이점은 무엇인가요?
- Function.prototype.bind을 설명하세요.
- this는 JavaScript에서 어떻게 작동하는지 설명해주세요.

* 자신이 속한 객체나 생성한 인스턴스를 가리키는 자기 참조 변수. (self-referencing variable)
* 함수를 호출하면 arguments 객체와 this가 암묵적으로 함수 내부에 전달.
* this 바인딩은 함수 호출 방식에 의해 동적으로 결정.
  🚨 다른 클래스 기반 언어는 클래스가 생성하는 인스턴스를 항상 가리킴.
* this 바인딩 : 식별자와 값을 연결하는 과정.
* 전역에서 this는 window.
* strict mode일 때 일 반 내부함수 내에서는 undefined.

| 함수 호출 방식                                                 | this 바인딩          |
| -------------------------------------------------------------- | -------------------- |
| 일반 함수                                                      | window               |
| 화살표 함수                                                    | 상위 스코프의 this   |
| 메서드 호출                                                    | 메서드를 호출한 객체 |
| 생성자 함수 호출                                               | 생성한 인스턴스      |
| Function.prototype.apply/call/bind<br> 메서드에 의한 간접 호출 | 인수에 의해 결정     |
