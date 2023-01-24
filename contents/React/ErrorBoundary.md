# ErrorBoundary

Error Boundary는 하위 컴포넌트 트리에서 발생한 에러를 잡아서 선언적으로 처리할 수 있는 컴포넌트입니다.

try-catch문과 비슷하게 렌더링 중에 throw 된 error를 catch 하도록 동작합니다.

</br>

## static getDerivedStateFromError()

이 생명주기 메서드는 하위의 자손 컴포넌트에서 오류가 발생했을 때 호출됩니다.
이 메서드는 매개변수로 오류를 전달받고, 갱신된 state 값을 반드시 반환해야 합니다.

</br>

🚨 getDerivedStateFromError()는 “render” 단계에서 호출되므로, 부수 효과를 발생시키면 안 됩니다.

</br>

## componentDidCatch()

이 생명주기 메서드는 자손 컴포넌트에서 오류가 발생했을 때에 호출되며, 2개의 매개변수를 전달받습니다.

- error - 발생한 오류
- info - 어떤 컴포넌트가 오류를 발생시켰는지에 대한 정보를 포함한 componentStack 키를 갖고 있는 객체

componentDidCatch()는 “커밋” 단계에서 호출되므로, 부수 효과를 발생시켜도 됩니다.

<br>

> 참고자료 <br> > [kakao-Frontend 기술 블로그 - React의 Error Boundary를 이용하여 효과적으로 에러 처리하기](https://fe-developers.kakaoent.com/2022/221110-error-boundary/)
