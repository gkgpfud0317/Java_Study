# **API**

**1. API 정의**

​	API(Application Programming Interface : 애플리케이션 프로그래밍 인터페이스

​	API(Application Programming Interface : 응용 프로그램 프로그래밍 인터페이스

​	1) 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스

###### 			주로 파일 제어, 창 제어, 화상 처리, 문자 제어 등을 위한 인터페이스를 제공합니다

​	2) 애플리케이션 소프트웨어를 구축하고 통합하기 위한 정의 및 프로토콜 세트

**절차적 언어 API**

대부분의 절차적 언어에서 API는 특정한 작업을 수행할 함수들의 집합을 규정하며, 특정 소프트웨어 구성 요소와 상호 작용할 수 있게 한다.

---

# **REST**

- REST (Representational State Transfer)의 약자

- REST란
  - 웹에 존재하는 모든 자원(이미지, 동영상, DB 자원)에 고유한 URI를 부여해 활용하는 것으로, 자원을 정의하고 자원에 대한 주소를 지정하는 방법론을 의미합니다

- REST 구성요소
  - 자원(Resource) , URI
    모든 자원은 고유한 ID를 가지고 ID는 서버에 존재하고 클라이언트는 각 자원의 상태를 조작하기 위해 요청을 보낸다
  - 행위(Verb) , Method
    클라이언트는 URI를 이용해 자원을 지정하고 자원을 조작하기 위해 Method를 사용한다. HTTP 프로토콜에서는 GET , POST , PUT , DELETE 같은 Method를 제공한다.
  - 표현(Representation)
    클라이언트가 서버로 요청을 보냈을 때 서버가 응답으로 보내주는 자원의 상태를 Representation이라고 한다. REST에서 하나의 자원은 JSON , XML , TEXT , RSS 등 여러형태의 Representation으로 나타낼수 있다.

- REST의 특징
  - 클라이언트 / 서버 구조 (Client-Server)
  - 무상태 (Stateless)
  - 캐시 처리 가능 (Cachealble)
  - 계층화
  - 인터페이스 일관성(Uniform Interface)
  - 자체 표현 구조
- REST의 장점
  - 쉬운 사용
  - 클라이언트 - 서버 역할의 명확한 분리
  - 특정 데이터 표현을 사용가능
- REST의 단점
  - 메소드의 한계
  - 표준이 없음

---

