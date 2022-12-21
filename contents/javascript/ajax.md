# Ajax

## 에상 질문

- AJAX에 관해 가능한 한 자세히 설명하세요.
- AJAX를 사용했을 때의 장단점에 대해 설명해주세요.
  🧷장점

1. 갱신하는 데 필요한 데이터만 서버로부터 전송받음 (불필요한 데이터 발생x).
2. 변경하지 않는 부분은 다시 렌더링하지 않는다. (깜빡이는 현상 x).
3. 통신이 비동기적으로 이루어지기 때문에 서버에게 요청을 보낸 이후 블로킹이 발생하지 않음.

   🧷단점

4. 페이지 이동없는 보안상의 문제. (XSS)
5. 동일 출처 정책 문제 (비동기 서버와 호출하기 때문에 Ajax로 수신하는 데이터를 누군가 조작하여 응답 데이터로 보낼 수 있다.) https://wiki.wikisecurity.net/guide:ajax_%EA%B0%9C%EB%B0%9C_%EB%B3%B4%EC%95%88_%EA%B0%80%EC%9D%B4%EB%93%9C
   https://koreascience.kr/article/JAKO200734516349758.pdf

6. 무분별하게 사용하면 서버의 부하가 늘어남.
7. 지원하지 않는 브라우저.
8. 히스토리 관리.

- JSON의 개념과 메서드를 설명하세요.

  클라이언트와 서버 간의 HTTP 통신을 위한 텍스트 데이터 포맷.
  자바스크립트의 객체 리터럴과 유사한 키와 값으로 구성된 순수한 텍스트
  **JSON.stringify**: 객체를 JSON 포맷의 문자열로 변화. (직렬화)
  **JSON.parse**: JSON 포맷의 문자열을 객체로 변환. (역직렬화)

- ***

## 주요 개념

- Ajax(Asychronous JavaScript and XML): JavaScript를 사용하여 브라우저가 서버에게 비동기 방식으로 데이터를 요청하고, 서버가 응답한 데이터를 수신하여 웹페이지를 동적으로 갱신하는 프로그래밍 방식

- XMLHttpRequest: 브라우저에서 비동기 통신을 위한 메서드와 프로퍼티를 제공하는 Web API;

---

## 참고자료

- https://poiemaweb.com/js-ajax
- https://poiemaweb.com/js-spa

## 관련 내용

- promise
