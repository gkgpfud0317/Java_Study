# **deleteById와 delete**

**deleteById**

- deleteById 는 내부적으로 delete 를 호출하고있다
- 넘어온 id 값으로 findById 를 사용하여 delete에 인자로 넘겨줄 데이터를 조회하고있다
- 넘어온 id 값이 null 인 경우는 EmptyResultDataAccessException를 발생시킨다



**delete**

- delete 코드는 entity 에 대해 null 체크를 한 후 Entity Manager를 통해 삭제를 진행하고 있다



**deleteById 장점**

- deleteById 를 사용하면 서비스 로직에서 메소드를 하나만 사용해도 조회와 삭제가 다 된다
- 내부적으로 id 에 대한 null 체크를 해주기 때문에 서비스 로직에서 id 의 null 체크를 하지 않았더라도 의도치 않은 NullPointerException 발생을 예방 할 수 있다



**FindById 와 delete 를 조합하는 장점**

- deleteById 는 내부적인 findById 조회 시 값이 없을 경우 EmptyResultDataAccessException이 발생된다
  - 하지만 FindById 를 직접 사용하면 예외처리를 커스텀하여 서버 개발자가 원하는 메세지를 클라이언트로 보내줄 수 있다는 장점 또한 있다