## **parameter(매개변수), argument(인자)**

**parameter** 

- 둘 사이에서 양편의 관계를 맺어주면서, 어떤 관계나 범위 안에서 여러가지 값으로 변할 수 있는 가변적 요소

- 메소드, 생성자를 선언 할 때 어떤 형태로 데이터 값이 들어올 지 정의해 줌



**argument**

- 메소드, 생성자를 호출 할 때 데이터를 매개변수에 값을 전달해줌



간단하게 정리하자면

**매개변수(Parameter)** : 메소드에서 전달 받은 값

**전달인자(Argument)** : 메소드 호출시에 전달되는 값

```java
public class ArgumentParameter() {
    
    public static int operation(int parameter) {
        parameter += 10;
        return parameter;		// Parameter
    }
    // 전달 받은 매개변수가 된다
    
    public static void main(String[] args) {
        int argument = 10;
        operation(argument);	// Argument
    }
    // 전달할 전달인자가 된다
    
}
```







