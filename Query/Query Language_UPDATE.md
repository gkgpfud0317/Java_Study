## Query Language_UPDATE

이미 존재하는 데이터를 수정할때 사용하는 쿼리문



**( 1 ) UPDATE 테이블명 SET 컬러명 = 변경할 값;**

-  테이블에 있는 모든 데이터의 컬럼의 값을 변경

특정한 데이터를 수정하기 위해서는 WHERE절을 사용해야 함

( 예 )

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  1   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  3   | Flynn  | f1@gmail.com |   2   |
|  4   |  Amie  | aa@naver.com |   1   |
|  5   | Corini | cc@naver.com |   2   |

```sql
UPDATE STUDENT SET ID = 2;
```



변경된 table 

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  2   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  2   | Flynn  | f1@gmail.com |   2   |
|  2   |  Amie  | aa@naver.com |   1   |
|  2   | Corini | cc@naver.com |   2   |

STUDENT table 의 ID컬럼의 모든 값이 2로 변경 된 것을 볼 수 있음



**( 2 )  UPDATE 테이블명 SET 컬럼명 = 변경할 값 WHERE 컬럼명 = 값;**

-  WHERE절에 맞는 데이터 값만 변경함

( 예 )

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  1   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  3   | Flynn  | f1@gmail.com |   2   |
|  4   |  Amie  | aa@naver.com |   1   |
|  5   | Corini | cc@naver.com |   2   |

```sql
UPDATE STUDENT SET name = sunghyun WHERE ID = 3;
```

변경된 테이블 값

|  ID  |   name   |    email     | grade |
| :--: | :------: | :----------: | :---: |
|  1   |   Nico   | 1@gmail.com  |   3   |
|  2   |   Lynn   | a@naver.com  |   2   |
|  3   | sunghyun | f1@gmail.com |   2   |
|  4   |   Amie   | aa@naver.com |   1   |
|  5   |  Corini  | cc@naver.com |   2   |

ID 컬럼의 값이 3인 데이터 값의 name 컬럼 값을 sunghyun으로 바꿔 준 것을 확인 할 수 있음



**( 3 ) UPDATE 테이블명 SET 컬럼명1 = 변경할 값1, 컬럼명2 = 변경할 값2**

WHERE 컬럼명 = 값; 

-  변경해야할 컬럼이 여러개일 때 콤마(,)를 사용하여 여러개의 값을 변경할 수 있음

( 예 )

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  1   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  3   | Flynn  | f1@gmail.com |   2   |
|  4   |  Amie  | aa@naver.com |   1   |
|  5   | Corini | cc@naver.com |   2   |

```sql
UPDATE STUDENT SET name = sunghyun, grade = 3 WHERE ID = 3;
```

변경된 table

|  ID  |   name   |    email     | grade |
| :--: | :------: | :----------: | :---: |
|  1   |   Nico   | 1@gmail.com  |   3   |
|  2   |   Lynn   | a@naver.com  |   2   |
|  3   | sunghyun | f1@gmail.com |   3   |
|  4   |   Amie   | aa@naver.com |   1   |
|  5   |  Corini  | cc@naver.com |   2   |

ID 컬럼의 값이 3인 데이터 값의 name 컬럼 값을 sunghyun으로 바꾸어 주고 grade의 컬럼 값을 3으로 바꾸어 준 것을 확인 할 수 있음

