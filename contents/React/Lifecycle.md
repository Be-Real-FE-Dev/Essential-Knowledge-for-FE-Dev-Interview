# Lifecycle

생명주기 메서드(Lifecycle method)는 컴포넌트의 각각의 단계에서 실행되는 커스텀 기능입니다. <br>
컴포넌트가 만들어지고 DOM에 삽입될 때(mounting), 컴포넌트가 업데이트될 때 및 컴포넌트가 DOM에서 마운트 해제될 때(unmounted) 혹은 제거될 때 사용할 수 있는 기능을 제공합니다.

<br>

![images_minbr0ther_post_7f8ed738-2f24-46bd-ab9f-2c7e7d7976e2_Untitled-3](https://user-images.githubusercontent.com/92196967/210913900-6b4ec1b0-56b1-424b-a76c-238f6cd24782.png)

- mount
  - constructor: 컴포넌트의 state값을 초기화
  - componentDidMount : DOM이 생성되었을 때
  - getDerivedStateFromProps : props로부터 파생된 state를 가져옵니다. 즉 props로 받아온 것을 state에 넣어주고 싶을때 사용.
  - render : 컴포넌트를 렌더링하는 메서드.
- update
  - componentDidUpdate : 가상 돔이 실제 돔에 반영된 직후에 호출함으로 새로 반영된 돔의 상태값을 가장 빠르게 가져올 수 있음.
  - shouldComponentUpdate : 성능 최적화를 위해 존재. 반환값은 boolean.
  - getDerivedStateFromProps : 컴포넌트의 props나 state가 바뀌었을때
- unmount
  - componentWillunmount : 컴포넌트가 소멸될 때 사용되는 메소드로 네트워크 요청이나 타이머 해제 등의 작업을 처리하기 좋다.

<br>

> 참고 <br> > https://velog.io/@minbr0ther/React.js-%EB%A6%AC%EC%95%A1%ED%8A%B8-%EB%9D%BC%EC%9D%B4%ED%94%84%EC%82%AC%EC%9D%B4%ED%81%B4life-cycle-%EC%88%9C%EC%84%9C-%EC%97%AD%ED%95%A0

[벨로퍼트와 함께하는 모던 리액트](https://react.vlpt.us/basic/25-lifecycle.html)
