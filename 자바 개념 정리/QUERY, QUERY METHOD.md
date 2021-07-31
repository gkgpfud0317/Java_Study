# QUERY, QUERY METHOD

**사용자 정의 쿼리** : JPA가 자동으로 생성하는 쿼리를 사용하는게 아닌 사용자가 정의한 대로 쿼리가 생성 혹은 데이터베이스에 종속적인 Native Query가 생성되는 것을 말함



#### **쿼리 메서드**

메소드이름을 분석해서 JPQL 쿼리를 생성하여 실행해주는 기능 ( 특정 키워드와 형식을 맞춰서 우리가 원하는 필드에 대한 쿼리를 스프링데이터 JPA가 대신 생성 )

- Entity의 필드명이 변경되면 인터페이스에 정의한 메서드 이름도 꼭 함께 변경해야 함

  -- > 변경하지 않으면 애플리케이션 실행지점에 오류 발생

- 조회 : find / read / query / get 키워드를 사용해 조회 ( 키워드만 다를 뿐 기능은 같음 -- > 조회 )
  - find . . . By : By 뒤에는 조회할 조건을 명시 ( 없으며 전체 데이터 조회 )
  - read . . . By
  - query . . . By
  - get . . . By
- Count
  - count . . . By : 데이터의 총 개수를 반환
  - 반환타입 : long
- Exists
  - exists . . . By : 존재 여부를 boolean으로 반환
  - 반환타입 : boolean
- 삭제
  - delete . . . By
  - remove . . . By
  - 반환타입 : long
- DISTICNT
  - (예시) findDistinct : 중복을 제거하여 반환
  - (예시) findMemberDistinctBy : By 뒤에 조건이 없으니 모든 Member에 대해 조회
- LIMIT
  - (예시) findFirst : 가장 첫 데이터 반환
  
  - (예시) findFirst : 처음부터 3개의 데이터를 반환
  
  - (예시) findTop
  
  - (예시) findTop3
  
    

**쿼리 메서드의 기능**

- 메소등 이름으로 쿼리 생성
- 메소드 이름으로 JPA NamedQuery 호출
- @Query 어노테이션을 통해 Repository 인터페이스에 쿼리 직접 정의



