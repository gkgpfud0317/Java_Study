# Query Language_GRANT(보안)

기능 :  사용권한 부여

사용자에게 해당 객체에 대한 특정 사용권한을 부여할 때 사용

권한 종류 : SELECT, INSERT, DELETE, UPDATE 등

< 표기형식 > 

```sql
GRANT 권한 ON 데이터 객체 TO 사용자명 [WITH GRANT OPTION];
```

DBA : 

```sql
GRANT SELECT, DELETE ON STUDENT TO User WIHT GRANT OPTION;
```

데이터베이스 관리자가 GRANT 명령으로 검색하고 삭제할 수 있는 권한을 User에게 부여함 . User 또한 WIHT GRANT OPTION을 통해 다른 사용자에게 똑같은 권한을 부여 할 수 있음.



User :

```sql
GRANT SELECT, DELETE ON STUDENT TO User2;
```

User이 User2에게 권한을 주는 코드