## useState

### useState 초기값으로 함수를 넣는 경우 와 함수 호출문을 넣었을 떄의 차이

초기값으로 함수를 넣는 경우는 연산하는 값이 복잡한 경우이다.

함수가 올 경우 매 렌더 시 실행시키지 않지만 함수호출문이 올 경우 렌더 시 실제 값은 최신 state값을 가지지만 함수가 실행되므로 지양하는 것이 좋다.

```js
const [state, setState] = useState(complicatedFunction());
```

위와 같이 선언될 경우, complicatedFunction이라는 함수는 매 rendering 마다 계속 호출되어서 성능적으로 문제가 생길 수 있다. 이를 보완하기 위해서 우리는 아래와 같이 작성할 수 있다.

```js
const [state, setState] = useState(() => complicatedFunction());
```

이와 같이 선언할 경우, 가장 첫 rendering 할때만 호출이 될 수 있다.

<br>

## useMemo

- 메모리제이션된 값을 반환.
- useMemo를 사용해 데이터를 저장하면 이는 메모리를 사용하는 것
- 의존성 배열에 따라 다시 실행.

```js
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

<br>

## useCallback

- 메모리제이션된 함수를 반환.
- 의존성 배열이 변해야 새로운 상태값이 반영된 함수를 반환.
- 컴포넌트 실행 전반에 걸쳐 함수를 저장할 수 있게 하는 훅.
- 동일한 함수 객체가 메모리의 동일한 위치에 저장되므로 비교할 수 있음.
- 함수는 정의되는 시점의 환경을 기억함.
- 참조하고 있는 state값의 변경을 알려주어야 함. (최신 state값 참조)

```js
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```
