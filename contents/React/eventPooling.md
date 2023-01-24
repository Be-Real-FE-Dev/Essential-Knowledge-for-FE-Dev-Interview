# event pooling

- Event Pool: "이벤트가 발생할때마다 Synthetic Event 객체를 생성하고 제거하고 하지 말고, Synthetic Event Pool을 만들어서 이벤트가 발생할때 이 Pool을 사용하면 어떨까?” 라는 아이디어로 만들어진 것이 바로 Event Pool 이라는 개념입니다.

- 이벤트가 처리되고 나면 GC가 이벤트 객체 메모리를 해제하는 작업이 필요하다. 근데 그러면 이벤트가 발생할 때마다 이벤트 객체를 생성하고 제거해야 한다. 그래서 **풀링을 통해 이벤트 발생 시 이벤트 객체를 재사용**한다. 단지 이벤트가 실행되고 다시 풀로 돌아갈 때 값을 null로 초기화한다.<br>
  🚨 이런 pool 방식을 사용하면 사용자들이 null 바뀌는 건지 알 수 없기 때문에 이벤트 풀링을 리액트 17버전부터는 더 이상 이벤트 풀링이 적용되지 않는다.

 <br>

> 참고 자료 <br>
> [오브젝트 풀링](https://whiny.tistory.com/17) <br>
> [React event system](https://blog.mathpresso.com/react-deep-dive-react-event-system-2-1d0ad028308b) <br>
> [공식문서 event pooling](https://reactjs.org/docs/legacy-event-pooling.html)
