# @NotNull @NotEmpty @NotBlank

**@NotNull**

- null 을 허용하지 않는다
- " " 허용한다

- CharSequence, Collection, Map 또는 Array 는 null 이 아니지만 비어 있을 수 있다

---

```java
NotNull : Null 값 체크
```



**@NotEmpty**

- null 허용하지 않는다
- " " 허용하지 않는다
- " " 스페이스 허용한다

- 해당 필드(ex.Collection, Map, array) 의 size, length 가 최소 0보다 커야한다

- CharSequence, Collection, Map 또는 Array 는 null 이 아니다
- 크기 / 길이가 0보다 크고 유효하다

---

```java
NotEmpty : Null, ""체크
```



**@NotBlank**

- null 허용하지 않는다
- " " 허용하지 않는다
- " " 스페이스 허용하지 않는다

- 이 어노테이션을 붙인 String 필드는 null 이면 안되고 trim 된 String 의 길이 역시 0보다 커야 한다
- 제한된 문자열은 null 이 아니다
- 0보다 크고 유효하다

---

```java
NotBlank : Null, "", 공백을 포함한 빈값 체크
```

