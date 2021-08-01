## Query Language_DELETE

테이블에 있는 데이터를 삭제할때 사용

**( 1 ) DELETE from 테이블명;**

- 테이블에 있는 모든 데이터를 삭제



**( 2 ) DELETE from 테이블명 WHERE 컬럼명 = 값;**

- WHERE절에 맞는 데이터 값만 삭제

( 예 )

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  1   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  3   | Flynn  | f1@gmail.com |   2   |
|  4   |  Amie  | aa@naver.com |   1   |
|  5   | Corini | cc@naver.com |   2   |

```sql
DELETE from STUDENT WHERE ID = 5;
```

변경된 table

|  ID  | name  |    email     | grade |
| :--: | :---: | :----------: | :---: |
|  1   | Nico  | 1@gmail.com  |   3   |
|  2   | Lynn  | a@naver.com  |   2   |
|  3   | Flynn | f1@gmail.com |   2   |
|  4   | Amie  | aa@naver.com |   1   |

ID 컬럼의 값이 5인 모든 컬럼 값을 삭제한 것을 알 수 있음