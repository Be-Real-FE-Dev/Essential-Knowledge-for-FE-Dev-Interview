# JWT(JSON Web Token)

JWT(JSON Web Token)는 당사자 간에 정보를 JSON 개체로 안전하게 전송하기 위한 간결하고 독립적인 방법을 정의하는 개방형 표준( RFC 7519 )입니다. 이 정보는 디지털 서명되어 있으므로 확인하고 신뢰할 수 있습니다. JWT는 비밀( HMAC 알고리즘 포함) 또는 RSA 또는 ECDSA 를 사용하는 공개/개인 키 쌍을 사용 하여 서명할 수 있습니다 .

- .을 기준으로 Header, Payload, Signature로 나누어 진다.
  - Header : 토큰의 타입과 해시 암호화 알고리즘 구성
  - Payload : 토큰에 담을 클레임 정보를 포함함.
  - Signature : Secret key를 포함하여 암호화. (사용자 정보를 기반으로 암호화)
    🚨Base64 암호화가 너무 쉽기 때문에
    ![jwt](https://user-images.githubusercontent.com/92196967/211952288-69dedd32-bfae-49ef-86a5-dd3bf206185d.png)

> https://jwt.io/
