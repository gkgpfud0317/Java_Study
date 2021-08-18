## Query Language_INSERT

데이터를 삽입할때 사용하는 쿼리문

( 1 ) INSERT INTO 테이블명 (컬럼명1, 컬럼명2, 컬럼명3) VALUSE (값1, 값2, 값32) 

- 각 컬럼명에 순서대로 값을 넣어준다. 이때 컬럼명의 개수와 값의 개수는 일치해야 함

또한 문자열을 입력하는 경우 작은따음표로 문자열을 감싸줘야 함

( 예 )

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  1   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  3   | Flynn  | f1@gmail.com |   2   |
|  4   |  Amie  | aa@naver.com |   1   |
|  5   | Corini | cc@naver.com |   2   |



기존 Table STUDENT에 새로운 데이터 값을 넣어주고 싶다면 커맨드

```sql
INSERT INTO STUDENT (ID, name, email, grade) VALUES (6, 'SungHyun', 'cshsmart24@naver.com',1);
```

변경된 table

|  ID  |   name   |        email         | age  |
| :--: | :------: | :------------------: | :--: |
|  1   |   Nico   |     1@gmail.com      |  3   |
|  2   |   Lynn   |     a@naver.com      |  2   |
|  3   |  Flynn   |     f1@gmail.com     |  2   |
|  4   |   Amie   |     aa@naver.com     |  1   |
|  5   |  Corini  |     cc@naver.com     |  2   |
|  6   | SungHYun | cshsmart24@anver.com |  1   |

이때 만약 코드가 아래와 같다면

```sql
INSERT INTO STUDENT (ID, name, email, grade) VALUES (6, 'SungHyun', 'cshsmart24@naver.com');
```

컬럼명의 개수와 값의 개수가 맞지 않는 다면 오류가 발생



( 2 ) INSERT INTO 테이블명 VALUES (값1, 값2, 값3)

- INSERT 문에서는 테이블명 다음에 컬럼명을 굳이 입력하지 않아도 됨

하지만 테이블에 있는 모든 컬럼의 수에 맞게 값을 입력해야 함

( 예 )

|  ID  |  name  |    email     | grade |
| :--: | :----: | :----------: | :---: |
|  1   |  Nico  | 1@gmail.com  |   3   |
|  2   |  Lynn  | a@naver.com  |   2   |
|  3   | Flynn  | f1@gmail.com |   2   |
|  4   |  Amie  | aa@naver.com |   1   |
|  5   | Corini | cc@naver.com |   2   |

기존 Table STUDENT에 새로운 데이터 값을 넣어주고 싶다면 커맨드

```sql
INSERT INTO STUDENT VALUSE (6, 'SungHyun', 'cshsmart24@naver.com',1)
```

변경된 table

|  ID  |   name   |        email         | age  |
| :--: | :------: | :------------------: | :--: |
|  1   |   Nico   |     1@gmail.com      |  3   |
|  2   |   Lynn   |     a@naver.com      |  2   |
|  3   |  Flynn   |     f1@gmail.com     |  2   |
|  4   |   Amie   |     aa@naver.com     |  1   |
|  5   |  Corini  |     cc@naver.com     |  2   |
|  6   | SungHYun | cshsmart24@anver.com |  1   |

이때 만약 코드가 아래와 같다면

```sql
INSERT INTO STUDENT VALUSE (6, 'SungHyun', 'cshsmart24@naver.com')
```

테이블에 있는 컬럼의 개수와 코드의 값의 개수가 일치하지 않으므로 오류가 발생
