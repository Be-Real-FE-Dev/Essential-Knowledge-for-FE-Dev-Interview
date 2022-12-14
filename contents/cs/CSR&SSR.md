# CSR & SSR

## CSR

- 정의 : Client Side Rendering의 약자로 렌더링을 클라이언트 쪽에서 담당하는 걸 뜻한다

  <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FctbYqm%2FbtrE8OfqPyZ%2FV89cr1aPQZemy8tNmnhLek%2Fimg.png"/>

- CSR 단계

  1. User가 Website 요청을 보냄.

  2. 서버는 빈 페이지(HTML, CSS)를 클라이언트에게 전달합니다. (해당 페이지에는 JS 링크가 포함되어 있습니다.)

  3. 전달받은 클라이언트에서 해당 화면을 그려주고 스크립트를 다운로드하여서 최종적인 화면을 사용자에게 보여줍니다. (해당 부분에서 사용자에게 보여준 뒤 JS를 로드해서 사용자에게 보이는 화면 속도가 느리다.)

  4. 사용자가 다음 액션을 수행하는 경우 클라이언트 내에서 페이지를 요청하고 수행합니다.

  - 적합성 : CSR은 대화형 및 동적 애플리케이션을 구축하는 데 더 적합
  - 장점 : 화면의 깜빡임이 없어 사용성이 좋으며 필요한 데이터만 요청하기 때문에 서버의 부하가 심하지 않다는 것

## SSR

- 정의 : Server Side Rendering의 약자로 서버쪽에서 렌더링 준비를 끝마친 상태로 클라이언트에 전달하는 방식이다.

  <img src="https://blog.kakaocdn.net/dn/bEmdtZ/btrn2274cKa/ZMRPUFOdz59bgKtwmwNwzK/img.png"/>

- SSR 단계

  1. User가 Website 요청을 보냄.

  2. Server는 'Ready to Render'. 즉, 즉시 렌더링 가능한 html파일을 만든다.(리소스 체크, 컴파일 후 완성된 HTML 컨텐츠로 만든다.)

  3. 클라이언트에 전달되는 순간, 이미 렌더링 준비가 되어있기 때문에 HTML은 즉시 렌더링 된다. 그러나 사이트 자체는 조작 불가능하다. (Javascript가 읽히기 전이다.)

  4. 클라이언트가 자바스크립트를 다운받는다.

  5. 다운 받아지고 있는 사이에 유저는 컨텐츠는 볼 수 있지만 사이트를 조작 할 수는 없다. 이때의 사용자 조작을 기억하고 있는다.

  6. 브라우저가 Javascript 프레임워크를 실행한다.

  7. JS까지 성공적으로 컴파일 되었기 때문에 기억하고 있던 사용자 조작이 실행되고 이제 웹 페이지는 상호작용 가능해진다.

- 적합성 : 일반적으로 SSR은 SEO 및 초기 페이지 로드 성능에 더 적합
- 장점 : seo 검색 최적화(점으로는 매번 페이지가 서버에서 미리 그려지고 보여주기 때문에 SEO에 유리)
- 단점 : 매번 요청을 하므로 서버의 부하가 심해지고 화면의 깜빡임이 있어 사용성이 나쁘다

## SPA & MPA

- SPA(Single Page Application): 하나의 html를 사용하는 기법.
  - CSR(Client Side Rendering)이라고 할 수 있다. CSR은 html로 ajax과 같은 비동기 통신을 통해 데이터를 가지고 와서 화면을 그려주는 방식
- MPA(Multiple Page Application): 다수의 html를 사용하는 기법.
  - SSR(Server Side Rendering)라고 할 수 있다. 이는 서버에 매 페이지마다 요청을 하여 화면에 보여주는 방식
    CSR ≠ SPA , SSR ≠ MPA

CSR은 client side rendering으로 클라이언트 측에서 JS파일을 다운 받 나서 HTML을 생성하기 위해 자바스크립트 코드를 실행해야 합니다. 이것은 초기 로드 시간을 더 느리게 만들 수 있지만, 더 동적이고 상호작용적인 페이지를 허용할 수도 있습니다.

SSR에서 페이지가 로드될 때 클라이언트가 페이지 내용을 이미 사용할 수 있으며, 클라이언트는 내용을 가져오기 위해 서버에 추가 요청을 할 필요가 없습니다. 이렇게 하면 특히 인터넷 연결 속도가 느린 사용자의 경우 페이지 성능을 향상시킬 수 있습니다.

Client Side Rendering은 동적으로 DOM을 생성한다.

Server Side Rendering 서버단에서 미리 DOM트리를 만들어 client 단으로 보내준다.

csr은 SPA 방식이 급부상하며 유용하게 사용된 렌더링 방식이다.

초기에 모든 리소스를 다운 받기에 초기렌더링이 느린 단점이 있지만 그 이후 유저와의 인터렉션에 있어 빠른 화면 전환으로 사용자 경험에 있어 좋다.

ssr은 필요한 리소스만 받아와 렌더링하기에 초기로딩속도가 짧으며 SEO에 장점이 있다.

해당 개념을 이해하기 위해서는 SPA와 MPA를 알 필요가 있다.

## CSR vs SSR 차이

1. 웹페이지를 로딩하는 시간
   웹 페이지 로딩의 종류는 두 가지로 나눌 수 있다.
   하나는 웹 사이트의 가장 첫 페이지를 로딩하는 것과 다른 하나는 나머지를 로딩하는 것

   - 첫 페이지 로딩시간

     - CSR의 경우 HTML, CSS와 모든 스크립트들을 한 번에 불러온다. 반면 SSR은 필요한 부분의 HTML과 스크립트만 불러오게 된다.

     - 따라서 평균적으로 SSR이 더 빠르다.

   - 나머지 로딩 시간

     - 첫 페이지를 로딩한 후, 사이트의 다른 곳으로 이동하는 식의 동작을 가정하자. CSR은 이미 첫 페이지 로딩할 때 나머지 부분을 구성하는 코드를 받아왔기 때문에 빠르다.

   - 반면, SSR은 첫 페이지를 로딩한 과정을 정확하게 다시 실행한다. 그래서 더 느리다.

2. SEO 대응
   검색 엔진은 자동화된 로봇인 '크롤러'로 웹 사이트들을 읽는다. CSR은 자바스크립트를 실행시켜 동적으로 컨텐츠가 생성되기 때문에 자바스크립트가 실행 되어야 meatadata가 바뀌었다.
   (이전 크롤러들은 자바스크립트를 실행시키지 않았었기에 SEO 최적화가 필수적이었다. 구글이 그 트렌드를 바꾸고 있다고 한다.)
   SSR은 애초에 서버 사이드에서 컴파일되어 클라이언트로 넘어오기 때문에 크롤러에 대응하기 용이하다.

3. 서버 자원 사용
   SSR이 서버 자원을 더 많이 사용한다. 매번 서버에 요청을 하기 때문이다.

<blockquote>
참고 | https://higher77.tistory.com/m/103
</blockquote>
