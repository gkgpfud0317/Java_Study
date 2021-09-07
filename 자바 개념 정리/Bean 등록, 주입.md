# Bean 등록, 주입

**( 1 ) XML을 이용한 빈 등록**

```java
<bean id = "aaa" class = "xxx.yyy.zzz.AAA">
	<property name = "prop"></property>
</bean>
```

XML <문제점>

- 빈의 성격 구분을 하기 힘듬
- 어플리케이션의 크기가 조금만 커져도 빈의 양이 늘어 관리 버거움



**( 2 ) -  1  Annotation을 이용한 빈 등록**

|             |                                                              |
| :---------- | ------------------------------------------------------------ |
| @Component  | 컴포넌트를 나타내는 일반적인 스테리오 타입으로 태그와 동일한 역할을 함 |
| @Repository | 퍼시스턴스 레이어, 영속성을 가지는 속성(파일, 데이터베이스)을 가진 클래스 |
| @Service    | 서비스 레이어, 비지니스 로직을 가진 클래스                   |
| @Controller | 프리젠테이션 레이어, 웹 어플리케이션에서 웹 요청과 응답을 처리하는 클래스 |

~ @Repository, @Service, @Controller는 더 특정한 유즈케이스 대한 @Component의 구체화 된 형태



**( 2 ) -  2  빈 의존관계 주입 Annotation**

|            |                                                              |
| :--------- | :----------------------------------------------------------- |
| @Autowired | 정밀한 의존관계 주입이 필요한 경우에 유용. @Autowired는 프로퍼티, setter 메서드, 생성자, 일반 메서드에 적용 가능. 의존하는 객체를 주입할 때 주로 Type 이용 |
| @Resource  | 어플리케이션에서 필요로 하는 자원을 자동 연결할 때 사용 @Resource는 poperty, setter 메서드에 적용 가능 의존하는 객체를 주입할 때 주로 Name을 이용 |
| @Value     | 단순한 값을 주입할 때 사용되는 annotation. @Value(“Spring”)와 동일한 역할 |
| @Qualifier | @Qualifier는 @Autowired annotation과 같이 사용. @Autowired는 타입으로 찾아서 주입하므로, 동일 타입의 Bean 객체가 여러 개 존재할 때 특정 Bean을 찾기 위해 사용 |

~ @Component를 통해 자동으로 Bean을 등록

~ @Autowired로 의존관계를 주입받는 어노테이션을 클래스에 선언하여 사용했을 경우 해당 크래스가 위치한 특정 패키지를 Scan하기 위한 설정을 XML에 해야함



**( 3 ) - 1 자바 코드로 빈 등록**

```java
@Configuration
public class ConfigurationBeanFactory {

	@Bean
	public CarInfoProvider kiaCar() {
		return new KiaCar();
	}
	
	@Bean
	public CarInfoProvider hyendaiCar() {
		return new HyundaiCar();
	}
	
}
```



**나머지 종류**

|                |                                                              |
| -------------- | :----------------------------------------------------------- |
| @Qualifer      | \- @Qualifier는 @Autowired 어노테이션과 같이 사용되어 진다.                          \- @Autowired는 타입으로 찾아서 주입하므로 동일한 타입의 Bean 객체가 여러개 존재할때 |
| @Bean          | \- @Bean 어노테이션은 새로운 빈 객체를 제공할때 사용되며 @Bean이 적용된 메서드의 이름을 Bean의 식별값으로 사용함 |
| @Configuration | \- 클래스에 @Configuration 어노테이션을 선언하는 것은 스프링 IoC 컨테이너가 해당 클래스를 Bean 정의의 설정으로 사용한다는 것을 나타냄 |



