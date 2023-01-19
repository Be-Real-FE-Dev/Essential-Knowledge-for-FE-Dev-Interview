# JSX

JSX는 JavaScript의 확장 문법입니다. JSX는 템플릿 언어와 비슷해 보이지만, JavaScript의 강력한 기능들을 모두 사용할 수 있습니다.
JSX는 React.createElement()의 호출을 통해 일반 JavaScript 객체인 “React 엘리먼트”(React element)로 컴파일됩니다. JSX에 대한 기본 소개는 [여기](https://ko.reactjs.org/docs/introducing-jsx.html)에서 확인할 수 있으며 JSX에 대한 자세한 튜토리얼은 [여기](https://ko.reactjs.org/docs/jsx-in-depth.html)에서 확인할 수 있습니다.

React DOM은 HTML 어트리뷰트(attribute) 이름 대신 캐멀케이스(camelCase)를 네이밍 컨벤션으로 사용합니다. 예를 들어, JSX에서 tabindex는 tabIndex로 작성합니다. class 어트리뷰트는 JavaScript의 예약어이므로 className으로 작성합니다.

```jsx
<h1 className="hello">My name is Clementine!</h1>
```
