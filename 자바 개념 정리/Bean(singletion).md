# @Bean(singletion)

**spring Bean**

![img](https://gmlwjd9405.github.io/images/spring-framework/spring-bean.png)

- Spring에서 POJO(Plain, Old Java Object)를 Bean 이라고 부름
- 애플리케이션의 핵심을 이루는 객체
  - 인스턴스화, 관리, 생성
- 우리가 컨테이너에 공급하는 설정 메타 데이터(XML)에 의해 생성
  - 이 메타 데이터를 통해 Bean의 생성, 종속성 등을 알 수 있음
- 애플리케이션의 객체가 지정되면, 해당 객체는 메소드를 통해 가져 올 수 있음



**Singleton**

![img](https://gmlwjd9405.github.io/images/spring-framework/spring-bean-singleton.png)

- 생성된 하나의 인스턴스는 single beans cache에 저장되고, 해당 bean에 대한 요청과 참조가 있으면 태시된 객체를 반환함
- 기본적으로 모든 bean은 scope이 명시적으로 지정되지 않으면 singleton임



**singleton의 문제점**

- 인터페이스가 아닌 구체 클래스에 의존하게 되며 SOLID를 위반하게 된다.
- 내부에 생성자가 있기 때문에 테스트하기 어렵다.
- private 생성자기 때문에 상속하기 불가능하다.
- 다형성을 사용하기 어렵고 객체지향과 거리가 멀어진다

*해결*

*하지만 스프링은 loC컨테이너가 선언된 빈들을 모두 관리해주고 thread Safety도 보장*