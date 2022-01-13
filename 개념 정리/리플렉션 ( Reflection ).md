# 리플렉션 ( Reflection )

**리플렉션**

- 객체를 통해 클래스의 정보를 분석해 내는 프로그램 기법 = 투영, 반사 라는 사전적인 의미
  - BeanFactory 어플리케이션이 실행한 후 객체가 호출 될 당시 객체의 인스턴스를 생성하게 되는데 그 때 필요한 기술 Reflection

- 구체적인 클래스 타입을 알지 못해서 그 클래스의 메소드와 타입 그리고 변수들을 접근 할 수 있도록 해주는 자바 API

  - 이 설명에 의하면 구제적인 클래스 타입을 모를때 사용하는 방법을 리플렉션

    - 여기서 이상한 점은 **내가 짠 코드인데 내가 만든 클래스의 이름도 모르는게 말이 되나?** 라는 점. 하지만 가끔 어떤 타입의 클래스나 변수 혹은 메소드를 사용 할 지 모르는 경우가 생김. 

    예 ) 변수의 값을 조건에 따라서 다르게 사용해야하는 경우 애플리케이션이 실행되고 나서 생성되는 클래스라던가 이럴경우 리플렉션을 사용 할 수 있음.

**< 사용방법 >** 1

Class 객체의 forName 메소드를 사용하여 클래스이름에 해당하는 클래스를 찾아옴. ClassNotFound 에러가 날 수 있음.

```java
Class c = Class.forName("클래스이름");

// 메소드
Method[] m = c.getMethods();

// 필드
Field[] f = c.getFields();

// 구조체
Constructor[] cs = c.getConstructors();
Class[] inter = c.getInterFaces();
Class superClass = c.getSuperclass();
```



**< 사용방법 >** 2

reflection은 자바의 특징. 실행중인 자바프로그램 내부를 검사하고 내부의 속성을 수정 할 수 있도록 함. 예 ) 어떤 자바 클래스가 가진 모든 멤버의 이름을 얻거나 보여줄 수 있음. 자바에서 클래스가 그 자신을 조사하고 수정하는 것이 많다고 할 수는 없으나 다른 언어에서는 볼 수 없는 특징. reflection이 구체적인 쓰임중에 하나가 빌더툴을 이용해서 소프트웨어 콤포넌트를 만드는 곳. 툴은 reflection을 사용해서 동적으로 로딩되는 자바 콤포넌트(클래스)의 속성을 얻을 수 있음

```java
import java.lang.reflect.Method;

public class DumpMethods {
	public static void main(String args[]) {
		try {
			Class c = Class.forName(args[0]);
			Method m[] = c.getDeclaredMethod();
			for(int i = 0; i < m.length; i++)
            	System.out.println(m[i].toString());
		} catch (Throwable e) {
			System.err.println(e);
		}
	}
}
```

이 프로그램은 java.util.Stack 의 속성과 반환값에 따라 메소드리스트를 출력. 이 프로그램은 Class.forName을 통해서 클래스를 로딩하고 getDeclaredMethods을 통해서 클래스에서 정의한 메소드리스트를 얻음. java.lang.reflect.Method는 단일 메소드를 나타내는 클래스