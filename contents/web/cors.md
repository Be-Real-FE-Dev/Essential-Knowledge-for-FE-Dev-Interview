# CORS(Cross-Origin Resource Sharing) & SOP(Same-Origin Policy)

### Origin

- Protocol + Domain + port
- 위의 세 가지가 같을 때 같은 출처.
- 서버의 위치를 찾아가기 위해 필요한 가장 기본적인 것들을 합쳐놓은 것.

![uri-structure](https://user-images.githubusercontent.com/92196967/211551520-f541c58f-6579-4a42-9cfd-15423b69791c.png)

<br>

### CORS

교차 출처 리소스 공유(Cross-origin resource sharing, CORS), 교차 출처 자원 공유는 웹 페이지 상의 제한된 리소스를 최초 자원이 서비스된 도메인 밖의 다른 도메인으로부터 요청할 수 있게 허용하는 구조이다. 웹페이지는 교차 출처 이미지, 스타일시트, 스크립트, iframe, 동영상을 자유로이 임베드할 수 있다.

다만 특정 교차 도메인 간(cross-domain) 요청, 특히 Ajax 요청은 동일-출처 보안 정책에 의해 기본적으로 금지된다.

- CORS가 동작하는 방식

1. Preflight Request

- 일반적으로 우리가 웹 어플리케이션을 개발할 때 가장 마주치는 시나리오
- 브라우저가 본 요청을 보내기 전에 보내는 예비 요청(Preflight)을 보내는 것.
- HTTP 메소드 중 OPTIONS 메소드가 사용

2. Simply Request

- 단순 요청은 예비 요청을 보내지 않고 바로 서버에게 본 요청부터 때려박은 후, 서버가 이에 대한 응답의 헤더에 Access-Control-Allow-Origin과 같은 값을 보내주면 그때 브라우저가 CORS 정책 위반 여부를 검사하는 방식
- 요청의 메소드는 GET, HEAD, POST 중 하나여야 한다.
- Accept, Accept-Language, Content-Language, Content-Type, DPR, Downlink, Save-Data, Viewport-Width, Width를 제외한 헤더를 사용하면 안된다.
- 만약 Content-Type를 사용하는 경우에는 application/x-www-form-urlencoded, multipart/form-data, text/plain만 허용된다.

3. Credentialed Request

- 인증된 요청을 사용하는 방법
- 다른 출처 간 통신에서 좀 더 보안을 강화하고 싶을 때 사용하는 방법

<br>

### SOP

같은 출처에서만 리소스를 공유할 수 있다”라는 규칙을 가진 정책
XMLHttpRequest, Fetch API → 기본적으로 Same-Origin 정책을 따름

### CORS 정책을 허용하여 에러 해결하는법

1. 클라이언트에서 HTTP요청의 헤더에 Origin을 담아 전달
   기본적으로 웹은 HTTP 프로토콜을 이용하여 서버에 요청을 보내게 되는데, 이때 브라우저는 요청 헤더에 Origin 이라는 필드에 출처를 함께 담아 보내게 된다.

   <br>

2. 서버는 응답헤더에 Access-Control-Allow-Origin을 담아 클라이언트로 전달한다.
   서버가 요청에 대한 응답을 할 때 응답 헤더에 Access-Control-Allow-Origin이라는 필드를 추가하고 값으로 '이 리소스를 접근하는 것이 허용된 출처'를 내려보낸다.

> https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-CORS-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95-%F0%9F%91%8F

### JSONP

다른 도메인에 접근할 수 있는 우회적인 기법 중에 JSONP(JSON with Padding) 방법이 있다. 웹 브라우저에서 실행되는 Javascript는 통신을 이용해 외부 출처에서 데이터를 받아오는 것이 불가능하지만, HTML

문법 오류가 발생하는 이유는 Javascript에서 변수, 상수로 정의 되지 않고 json형식이 입력되면서 발생한다.

JSONP는 이러한 웹브라우저 특성을 이용하여 json 데이터를 서버가 콜백함수로 감싸 javascript 문법을 유효하게 만들어 전달하여 클라이언트에서 응답을 받을 수 있게 됩니다.

"http://server.example.com/User/1234"요청을 예로 든다면

parseResponse 콜백함수를 JSONP 요청을하기위해 포함을 한다.

```html
<script type="application/javascript"
  src=http://server.example.com/Users/1234?callback=parseResponse">
</script>
```

외부의 서비스인 server.example.com은 JSON 데이터를 패딩하여 클라이언트에 전송합니다.

```js
parseResponse({ Name: 'Foo', Id: 1234, Rank: 7 });
```

JSONP 내용을 확인해보시면 아시겠지만 결국 서버에서 패딩을 요청한 콜백함수로 감싸줘 전송을 해야한다는 문제가 발생한다. 외부 API에서 콜백함수를 제공하지 않는다면 사용할 수 없는 방법이다.

### Proxy

![cors해결: proxy설정](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbld2Ht%2FbtqP4mzXDnD%2F2aqXhVA0Ymk7OUJafr5pB0%2Fimg.png)

서버에서 요청을 하게될 때에는 브라우저의 규약인 CORS 정책에 영향을 받지 않습니다. 그러한 이점을 이용하여 Proxy Server라는 출처를 통하기 때문에 CORS 정책을 위반하지 않게되어 우회 할 수 있게됩니다.

Express 서버일 경우 express-http-proxy 미들웨어를 통해서 간단하게 Proxy Server를 구현할 수 있습니다.

```js
var proxy = require('express-http-proxy');
var app = require('express')();

app.use('/proxy', proxy('www.text.com'));
```

좋아요6
공유하기게시글 관리

https://devport.tistory.com/13
