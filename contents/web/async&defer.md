# script 비동기 로드

## async

- HTML 파싱과 외부 자바스크립트 파일의 로드가 비동기적으로 동시에 진행됨
- 파싱과 실행은 자바스크립트 파일의 로드가 완료된 직후 진행, 이때 HTML 파싱이 중단됨
- 여러 개의 script 태그에 async 어트리뷰트를 지정하면 script 태그 순서와는 상관없이 로드가 완료된 js부터 먼저 실행 되므로 <strong>순서가 보장되지 않음.</strong>
- IE10 이상에서 지원됨

## defer

- HTML 파싱과 외부 자바스크립트 파일의 로드가 비동기적으로 동시에 진행됨
- 파싱과 실행은 HTML 파싱이 완료된 직후, 즉 DOM 생성

![async&defer](http://www.growingwiththeweb.com/images/2014/02/26/async-vs-defer-twitter.png)
