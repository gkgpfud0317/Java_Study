#  JPA(Java Persistence API)

**JPA**

- 자바 ORM 기술에 대한 표준 명세,  JAVA에서 제공하는 API

- 자바 어플리케이션에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스

  - 중요히 여겨야 할 부분 : JPA는 특정 기능을 하는 라이브러리가 아님

- JPA 인터페이스를 구현한 대표적인 오픈소스가 Hibernate

  ![img](https://gmlwjd9405.github.io/images/inflearn-jpa/implementation-of-jpa.png)

- ORM 이기 때문에 자바 클래스와 DB테이블을 매핑 

  - **ORM**이란? : DB 테이블을 자바 객체로 매핑함으로써 객체간의 관계를 바탕으로 SQL을 자동으로 생성하지만 Mapper는 SQL을 명시

    

**JPA특징**

- 데이터를 객체지향적으로 관리할 수 있기에 개발자는 비즈니스 로직에 집중할 수 있고 객체지향 개발가능
- 자바 객체와 DB 테이블 사이의 매핑 설정을 통해 SQL 생성
- 객체를 통해 쿼리를 작성할 수 있는 기능을 지원
- JPA는 성능 향상을 위해 지연 로딩이나 즉시 로딩과 같은 몇가지 기법을 제공하는데 이것을 잘 활용하면 SQL을 직접 사용하는 것과 유사한 성능을 얻을 수 있음



### **JPA를 왜 사용해야 할까**

- #### ( 1 ) SQL 중심적인 개발에서 객체 중심적인 개발 가능
  
  - SQL 코드의 반복, 객체지향과 관계지향 데이터베이스의 페러다임 불일치
  - Object - > [SQL 변환] - > RDB에 저장
  
- #### ( 2 ) 생산성이 증가
  
  - 간단한 메소드로 CRUD 가능
    - 간단한 CRUD 살펴보기
      - 저장 : jpa.persist(member)
      - 조회: Member member = jpa.find(memberId)
      - 수정: member.setName("변경할 이름")
      - 삭제: jpa.remove(member)
  
- #### ( 3 ) 유지보수가 쉬움
  
  - 기존 : 필드 변경 시 모든 SQL을 수정
  - JPA : 필드만 추가 하면 됨, SQL은 JPA가 처리하기 때문에 손 댈 것이 없음
  
- #### ( 4 ) Object 와 RDB (Relational Database)간의 패러다임 불일치 해결

  -  JPA와 상속

    ![img](https://gmlwjd9405.github.io/images/inflearn-jpa/rdb-super-sub-relation.png)

- #### ( 5 ) **JPA 성능 최적화**

- 기본적으로 중간 계층이 있는 경우 아래의 방법으로 성능을 개선 할 수 있는 기능이 존재
  - 1 ) 모아서 쓰는 버퍼링 가능
  - 2 ) 읽을 때 쓰는 캐싱 가능

**JPA 영속성**

- 데이터를 생성한 프로그램이 종료되어도 사라지지 않는 데이터의 특성을 말함

- 영속성을 갖기 않으면 데이터는 메모리에서만 존재하게 되고 프로그램 종료되면 해당 데이터는 사라지게 됨

- 데이터를 파일이나 데이터베이스에 영구 저장함으로써 데이터에 영속성을 부여

  

**JPA 동작과정**

![img](https://gmlwjd9405.github.io/images/inflearn-jpa/jpa-basic-structure.png)

- JPA는 애플리케이션과 JDBC 사이에서 동작

  - 개발자가 JPA를 사용하면, JPA 내부에서 JDBC API를 사용하면 SQL을 호출하여 DB와 통신

    

**JPA 저장과정**

![img](https://gmlwjd9405.github.io/images/inflearn-jpa/jpa-insert-structure.png)

- ex) memberDAO에서 객체를 저장하고 싶을때

  - 개발자는 JPA에 member 객체를 넘김

    - JPA

      - 1 ) member 엔티티를 분석

      - 2 ) INSERT SQL 생성

      - 3 ) JDBC API 사용하여 SQL을 DB에 날림

        

**JPA 조회과정**

![img](https://gmlwjd9405.github.io/images/inflearn-jpa/jpa-select-structure.png)

- ex) member 객체를 조회하고 싶을 때 
  - 개발자는 member 의 pk 값을 JPA에 넘김
  - JPA
    - 1 ) 엔티티의 매핑 정보를 바탕으로 적절한 SELECT SQL을 생성
    - 2 ) JDBC API를 사용하여 SQL을 DB에 날림
    - 3 ) DB로부터 결과 받아옴
    - 4 ) ResultSet를 개체에 모두 매핑함
- 쿼리를 JPA가 만들어 주기 때문에 Object RDB 간의 패러다임 불일치를 해결 할 수 있음

---

