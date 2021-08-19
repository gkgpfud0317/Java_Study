# JWT 

**JWT(Json  Web Token)**

- JSON 포맷을 이용한 Web Token
- 두 개체에서 JSON 객체를 이용해 Self-contained 방식으로 정보를 안전하게 전달
- 회원 인증, 정보 전달에 주로 사용

**Web Token의 필요성**

- 웹 토큰의 필요성
  - 기존 시스템의 보안 문제
  - 도메인 확장시 api로서의 문제
  - web, mobile 등 다양한 클라이언트
  - session 한계
  - scale out 한계
  - REST API : Stateless 지향

![img](https://github.com/KoEonYack/Tistory-Coveant/blob/master/Article/WebTech/jwt%EB%9E%80/img/c_2.PNG?raw=true)

**JWT 구조**

- Header(헤더)

  - 헤더는 JWT 토큰을 어떻게 해석해야 하는지를 알려주는 부분

- Payload(내용)

  - payload 종류 1 : 등록된 클래임(Registered Claim Names)

  - payload 종류 2 : 공개 클래임(Public Claim)

    사용자 정의 클레임으로 공개용 정보를 위해 사용

    충돌 방지를 위해 URI 포맷을 이용해야 함

  - payload 종류 3 : 비공개 클래임(Private Claim)

    등록된 클래임도 아니며 공개 클래임도 아닌 서버와 클라이언트 사이에 임의로 지정한 정보를 저장하기 위해 만들어진 사용자 지정 클래임

    비공개 클래임을 조심해서 사용하지 않으면 등록된 클래임과 공개 클래임도 다르게 충돌이 일어날 수 있기에 주의요함

- Signature(서명)

  - 헤더와 페이로드는 암호화 한 것이 아니라 단순히 JSON 문자열을 base64로 인코딩한 것
  - 누구나 디코딩을 한다면 헤어도아 페이로드의 내용을 볼 수 있음
  - 누군가 JWT를 탈취하여 수정한 후 서버로 보낼 수 있음. 이경우에 대비에 다른 사람이 위변조 했는지 검증하기 위한 부분
  - 서명은 헤더의 인코딩 값, 정보의 인코딩 값을 합친 후 비밀키로 해쉬를 하여 생성

**JWT 사용과정**

![img](https://media.vlpt.us/images/geunwoobaek/post/260558d1-80dc-467f-b2af-39bd12bf7df0/image.png)

1) 브라우저의 로그인과정에서 회원정보를 입력(ID, PASSWORD)

2) 서버는 JWT를 만듬

3) 서버는 브라우저에게 JWT를 보냄

4) 브라우저는 JWT를 가지고 서버에게 데이터를 요청

5) 서버는 서명을 확인하고 유저 정보를 클라이언트에게 제공함

**Access Token / Refresh Token**

- 액서스 토큰(Access Token)
  - 리소스에 직접 접근할 수 있도록 해주는 정보만을 가지고 있음
  -  Refresh Token에 비해서 짧은 만료 기간을 갖음
- 리프래시 토큰(Refresh Token)
  - 새로운 Access Toekn을 발급받기 위한 정보를 갖음
  - 클라이언트 Access Token이 없거나 만료되면 Refresh Token을 통해 Auth Server에 요청해서 새로운 Access Token을 발급 받을 수 있음
  - Access Token 에 비해서 긴 만료 기간을 갖음
  - 외부에 노출되지 않도록 관리를 위해서 데이터베이스에 저장

**JWT 사용목적**

- 회원인증 : JWT를 이용해서 회원정보를 주고 받게 되면 유저의 정보를 세션에 유지할 필요가 없게 됨. 즉 stateless 한 서버를 만들 수 있게 도와줌. 이전방식은 브라우저와 서버의 세션영역에 로그인 정보가 저장되어있는 Statefull 한 서버
- 정보교류 : 데이터를 주고받을때 안정성있게 정보 교환할 수 있게 도와줌

**JWT 장/단점**

- 장점
  - 확장성
  - 보안성
  - 여러 도메인
  - 웹 앱 간의 상이한 쿠키 세션 처리
- 단점
  - 데이터 증가에 따른 네트워크 부하 증가
  - self-contained
  - Payload 인코딩
  - Stateless
