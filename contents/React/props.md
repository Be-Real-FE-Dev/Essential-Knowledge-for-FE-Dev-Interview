# Props

## Props Drilling

정의: `Prop Drilling`은 props를 오로지 하위 컴포넌트로 전달하는 용도로만 쓰이는 컴포넌트들을 거치면서 React Component 트리의 한 부분에서 다른 부분으로 데이터를 전달하는 과정이다.

문제점: prop을 전달하는 과정이 많아질수록 코드를 읽을 때 해당 prop을 추적하기 어려워진다. 이는 곧 유지보수의 어려움을 야기시킨다.

해결방안:

### 1. 상태관리 라이브러리 사용(Redux, MobX, Recoil 등)

### 2. 컴포넌트 합성 사용

컴포넌트에서 다른 컴포넌트를 담는 것이 합성이다.
어떤 컴포넌트들은 어떤 자식 엘리먼트가 들어올 지 미리 예상할 수 없는 경우가 있다. 예를 들어, 모달 컴포넌트 등에서 찾아볼 수 있는데, 이러한 컴포넌트에서는 `children prop`을 사용하여 자식 엘리먼트를 출력에 전달할 수 있다.

[참고자료](https://velog.io/@jangws/React-Context%EA%B0%80-%EA%BC%AD-%ED%95%84%EC%9A%94%ED%95%A0%EA%B9%8C-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%ED%95%A9%EC%84%B1%EC%9C%BC%EB%A1%9C-props-drilling%EC%9D%84-%EA%B7%B9%EB%B3%B5%ED%95%B4%EB%B3%B4%EC%9E%90)
