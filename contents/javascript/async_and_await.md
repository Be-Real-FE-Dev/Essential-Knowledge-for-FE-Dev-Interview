# async/ await

### async 함수

- async 키워드를 사용해 정의하며 언제나 프로미스를 반환한다.
- async 함수가 명시적으로 프로미스를 반환하지 않더라도 async 함수는 암묵적으로 반환 값을 resolve하는 프로미스를 반환한다.

### await 키워드

- await 키워드는 프로미스가 settled 상태(비동기 처리가 수행된 상태) 가 될 때까지 대기하다가 settled 상태가 되면 프로미스가 resolve한 처리 결과를 반환한다.
- await 키워드는 반드시 프로미스 앞에서 사용해야 한다.

### Promise와 async/await의 차이점

① 에러 핸들링

Promise 를 활용할 시에는 .catch() 문을 통해 에러 핸들링을 해야 하지만,
async/await 은 try / catch를 통해
에러를 처리할 수 있다.

② 코드 가독성

Promise의 후속 처리 메서드인 .then() 의 hell의 가능성
async/await 은 프로미스의 후속 처리 메서드 없이 마치 동기 처리처럼 프로미스가 처리 결과를 반환하도록 구현할 수 있기 때문에 코드 흐름을 이해 하기 쉽다.
