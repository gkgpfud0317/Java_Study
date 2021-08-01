# Query Language_REVOKE(보안)

기능 :  사용권한 취소

사용자에게 해당 객체에 대해 특징 사용권한을 취소할 때 사용

권한 종류 : SELECT, INSERT, DELETE, UPDATE 등

<표기형식>

```sql
REVOKE [GRANT OPTION FOR] 권한 ON 데이터 객체 FROM 사용자명 [CASCADE];
```

( 예 )

```sql
REVOKE SELECT, DELETE ON STUDENT FROM User CASCADE;
```

CASCADE User이라는 사용자가 다른 사용자에게 준 권한까지 연쇄적으로 뺏을 때 사용

