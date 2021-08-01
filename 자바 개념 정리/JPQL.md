# JPQL

JPQL 은 SQL 과 비슷한 문법을 가진 객체 지향 쿼리임.

JPQL 의 탄생배경은 JPA 에서 제공하는 메서드 호출만으로 섬세한 쿼리 작성이 어렵다는 것. 이전 글 CRUD에서는 SELECT 쿼리를 위해 JPQL 을 사용했지만, EntityManager 객체의 find() 메서드를 호출하여 SELECT 쿼리를 수행 할 수도 있음.

```java
Book book = em.find(Book.class, 1);
```

find() 메서드는 식별자를 통해서만 데이터 조회를 하며, 조건문도 없고 모든 컬럼을 조회하는 메서드. 이것만 가지고는 **조금이라도 복잡한 검색을 수행할 수 없음**. 따라서 여러 조건을 통해 검색을 하는 방법이 필요했고, 그래서 JPQL이 개발



**JPQL의 특징**

- 테이블이 아닌 객체를 검색하는 객체지향 쿼리
- SQL 을 추상화 했기 때문에 특정 벤더에 종속적이지 않음
- JPA 는 JPQL 을 분석하여 SQL 을 생성한 후 DB 에서 조회



**기본문법**

```java
String jpql = "select c from Category c ";
```

JPQL 은 SQL 과 문법이 매우 유사하지만 몇 가지 다른 점이 있음

( 1 ) 대소문자 구분

엔티티와 속성은 대소문자를 구분. 예 ) 엔티티 이름인 User, User 엔티티의 속성인 email은 대소문자를 구분함. 반면에 SELECT, FROM, AS 같은 JPQL 키워드는 대소문자를 구별하지 않음.

( 2 ) 엔티티 이름

위의 예제에서 select c from 뒤에 나오는 Category 는 엔티티 이름. Category 가 클래스 이름이라고 착각할 수 있는데, 그것이 아니라 @Entity(name = "Category")로 설정한 엔티티 이름. 탐고로 name 속성을 생략하면 기본 값으로 클래스 이름을 사용함.

( 3 ) 별칭

select c from Category c 에서 c라는 별칭을 주었음. JPQL 에서 엔티티의 별치은 필수적으로 명시해야 함. 별칭을 명시하는 AS 키워드는 생략할 수 있음. 



JPQL 은 복잡한 검색을 위해 사용되기 때문에 INSERT, UPDATE, DELETE 쿼리는 엔티티 매니저가 직접 호출하도록 하는 것이 좋음.