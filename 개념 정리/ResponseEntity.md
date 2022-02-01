# ResponseEntity

**ResponseEntity**

- 응답 자체의 독립된 값이나 표현형태
- HttpEntity<T>를 상속받으며, RestRemplate 및 @Controller 메서드에 사용하고 있다
  - RestTemplate : 서버와 서버간 통신을 쉽게 해 줌
- HTTP 응답을 빠르게 만들어주기 위한 객체

- @ResponseBody 와 달리 어노테이션이 아닌 객체로 사용된다
- 응답으로 변환될 정보를 모두 담은 요소들을 객체로 만들어서 반환 시켜준다

- 이것은 HTTP 요청(Request) 또는 응답(Response) 에 해당하는 HttpHeader 와 HttpBody 를 포함하는 클래스
- 개발자가 직접 결과 데이터와 HTTP 상태 코드를 직접 제어할 수 있는 클래스
- 개발자는 404나 500 ERROR 와 같은 HTTP 상태 코드를 전송하고 싶은 데이터와 함께 전송할 수 있기 때문에 좀 더 세밀한 제어가 필요한 경우 사용한다



---

HttpEntity 클래스르 상속받아 구현한 클래스가 RequestEntity, ResponseEntity 클래스