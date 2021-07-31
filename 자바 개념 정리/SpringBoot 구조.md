# SpringBoot 구조

### **Controller**

- 사용자의 요청이 진입하는 지점
- 요청에 따라 어떤 처리를 할지 결정해줌
  - 단, controller : 결정만 해주고 실질적인 처리는 서비스에서 담당
- 사용자에게 View를 응답으로 보내줌

##### **Controller 쓰는 이유**

- 갈수록 처리해야 할 서비스들이 많아지는데, 이를 하나의 클래스에서 몰아 처리할 것이 아닌 Controller 라는 **중간제어자 역할**을 만들어 Controller가 필요한 로직 처리를 위한 서비스 호출

##### **Controller(web) 기능**

- 해당 요청 url에 따라 적절한 view와 mapping 처리
- 적절한 ResponseEntity(DTO)를 body에 담아 Client 에 반환

[정리]

\- Controoler는 웹 브라우저의 요청의 전담하여 처리

\- Controller가 Service 호출

---

### **service**

- service 역할은 DAO 가 DB 에서 받아온 데이터를 전달받아 가공하는 것

[정리]

\- Service 는 비지니스 로직을 수행

\- DB 에 접근하는 DAO 을 이용해서 결과값을 받아옴

---

#### **DAO(Data Access Object)**

- repository package
  - 실제로 DB에 접근하는 객체  // (Persistence Layer)이다.

- 실제 데이터베이스를 연결하는 역할
  - service 와 DB 를 연결하는 고리
- JPA에서는 DB에 데이터를 CRUD 하는 Repository 객체
  - JPA 대부분의 기본적인 CRUD method를 제공

[정리]

\- DAO 는 DB 에 접속하여 비즈니스 로직 실행에 필요한 쿼리를 호출

---

#### **DTO(Date Transfer Object)**

![img](https://media.vlpt.us/images/ohzzi/post/4cec2790-be9f-4263-96ee-704325bbeac1/spring-package-flow.png)

- 계층 간 데이터 교환 역할을 위한 객체

  - DB에서 데이터를 얻어 Service나 Controller 등으로부터 보낼때 사용하는 객체
  - 로직을 갖고 있지 않은 순수한 데이터 객체
  - 하지만 DB에서 꺼낸 값을 임의로 변경할 필요가 없기 때문에 DTO클래스에는 setter가 없음

- DB에서 꺼낸 데이터를 저장하는 Entity를 가지고 만드는 일종의 Warpper라고 볼 수 있음

  - Entity를 Controller 같은 클라이언트단과 직접 마주하는 계층에 직접 전달하는 대신 DTO

    데이터 교환

[정리]

\- 각 계층이 데이터를 주고 받을 때 사용하는 **객체**를 말함

여기서, 각 계층이란 View, Controller, DAO, DB를 말함

---

#### **domain(entity)**

- Entity 클래스는 DB의 테이블에 존재하는 Column 들을 필드로 가지는 객체를 말함
  - DB의 테이블과 1대 1로 대응되며, 때문에 테이블이 가지지 않는 컬럼을 필드로 가져서는 안됨
  - Entity 클래스는 다른 클래스를 상속받거나 인터페이스의 구현체여서는 안됨

**domain package**

- 실제 DB의 테이블과 매칭될 클래스
- 최대한 외부에서 Entity 클래스의 getter method를 사용하지 않도록 해당 클래스 안에서 필요한 로직 method 구현
- Entity 클래스와 DTO 클래스를 분리하는 이유

---



