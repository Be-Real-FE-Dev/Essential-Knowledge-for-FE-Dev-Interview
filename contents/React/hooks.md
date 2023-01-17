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

### react v18에서 자동 배칭의 변경점

Batching이란 React가 더 나은 성능을 위해 여러개의 state 업데이트를 한 번의 리렌더링으로 묶어서 진행하는 것을 말한다.

리액트 v18 이전은 외부 소스(fetch, setTimeout 등)에 대해서는 일괄처리를 해주지 않았다. 그래서 성능 개선을 위하여 외부 소스 코드를 사용할때는 ReactDOM.unstable_batchedUpdates를 사용해줬었다.
리액트 v18의 경우 ReactDOM.createRoot을 사용하게 되면 내부 소스, 외부 소스 Automatic Batching이 적용되어 있어 신경 쓰지 않아도 된다.

자동배칭을 원하지 않는 경우 ReactDOM.flushSync()를 사용하여 제외할 수 있다.

[Automatic batching for fewer renders in React 18](https://github.com/reactwg/react-18/discussions/21)
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
