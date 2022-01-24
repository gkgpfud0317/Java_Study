# save()

**save()**

- 스프링 데이터 JPA 에서는 기본적으로 JpaRepository 를 통해 DB 와 상호작용 하게 된다
- JpaRepository 는 save 메서드를 통해 DB 에 엔티티 정보를 저장하게 된다
- save 메서드는 단순히 새 entity 를 DB 에 추가하는 것이 아니고 entity 의 상태에 따라 다른 동작방식을 보인다. 아래의 조건에 따라 엔티티를 관리해주는 EntityManager 는 엔티티의 상태를 추적해서 DB 에 반영할지 아니면 업데이트를 할 지 결정하게 된다

- 업데이트를 위한 용도로도 사용 될 수 있다
- entity의 @Id property 를 찾고 해당 property 가 null 이면 transient 상태로 판단하고 null 이 아니면 detached 로 판단한다



**Entity 생명주기**

- transient : 새롭게 만들어진 객체. 하이버네이트나 DB 둘다 얘의 정보를 모른다
- persistent : 영속성이라고도 불리우는 상태. persistent 컨텍스트가 관리를 하는 상태이다. 상태를 관리하거나 상태라면 필요한 경우 DB 에 싱크를 한다
- detached : 한 번이라도 db 에 persistent 가 되었던 객체이다. 즉 이 객체의 id 가 테이블에 매핑이 되는 경우

