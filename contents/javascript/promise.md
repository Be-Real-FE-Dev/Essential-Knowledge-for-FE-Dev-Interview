# Promise

- Promise 객체는 비동기 작업이 맞이할 미래의 완료 또는 실패와 그 결과 값을 나타냅니다.

- 비동기 동작을 다루기 위한 패턴으로, 비동기 요청을 보내면 성공 또는 실패가 다양한 형태로 발생한다.
  프로미스를 사용하면 이러한 성공(resolve)이나 실패(reject)를 편리한 방식으로 return할 수 있다.
  new 연산자와 함께 호출한 promise의 인자로 넘겨주는 콜백함수는 호출할 때 바로 실행, 그 내부에 resolve 또는 reject 함수를 호출하는 구문이 있으면 둘 중 하나가 실행되기 전까지는 다음 then or catch 구문으로 넘어가지 않는다. pending, fulfilled, rejected 3가지 상태를 가진다.

- <strong>Promise 는 콜백 헬로 인한 가독성 저하와 에러처리를 위해 도입되었다.<strong/>

<br>

### Promise 인스턴스 메서드

- then : 두 개의 콜백 함수를 인자로 전달 받는다. 프로미스 반환.
- catch : 예외(비동기 처리에서 발생한 에러와 then에서 발생한 에러)가 발생하면 호출. 프로미스 반환.
- finally : 프로미스의 이행과 거부 여부에 상관없이 항상 호출. 새로운 프로미스 반환.

<br>

### Promise 정적 메서드(static method)

- Promise.all : 배열과 같은 이터러블을 인자로 전달 받아 병렬로 처리. 처리 결과를 resolve하는 새로운 프로미스 반환. 처리 순서 보장. 가장 먼저 실패한 에러 프로미스 반환
- Promise.allSettled
- Promise.any
- Promise.race : 이터러블을 인자로 전달 받아 가장 먼저 처리된 결과를 새로운 프로미스로 반환.
- Promise.reject : 인자로 전달된 값을 reject하는 프로미스를 생성.
- Promise.resolve : 인자로 전달된 값을 resolve 값으로 반환
