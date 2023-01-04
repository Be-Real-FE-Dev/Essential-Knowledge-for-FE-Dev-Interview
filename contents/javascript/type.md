# 원시타입과 객체타입

자바스크립트에는 원시타입과 객체 타입이 있다.

- 원시타입(불변값) : String, Number, Boolean, undefined, null, Symbol, bigInt

- 참조타입 : Object, Array, Function

원시타입은 값에 의한 참조.

참조타입은 메모리 주소에 의한 참조. 참조 타입들은 무한하게 커질 수 있기 때문에 메모리에 주소를 저장하여 참조하는 것이다.

## null과 undefined의 차이

1. null
   null은 NULL의 심볼이며, 의도를 갖고 변수에 null을 할당하여 값이 없다는 것을 나타낸다. null이 할당된 변수의 타입을 확인해 보면 object인걸 확인할 수 있다.

```js
let a = null;
console.log(a); // null

console.log(typeof a); // object
```

2. undefined
   변수를 선언하고 값을 할당하기 전의 형태(값)라고 볼 수 있다. (\*변수에 값이 할당되어 있지 않음.)

```js
let b;
console.log(b); // undefined
```

정리

- undefined: 접근 가능한 스코프에 변수가 선언되었으나 현재 아무런 값도 할당되지 않은 상태이다. 타입을 확인해 보면 'undefined' 이다.
- null: 변수를 선언하고 'null'이라는 빈 값을 할당한 경우이다. 타입을 확인해 보면 'object' 이다.
