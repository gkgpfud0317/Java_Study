# SQL 문법

**CREATE**

- 테이블 생성

  create table student (

  칼럼명 타입 조건(not null),

  칼럼명 타입 조건(not null),

  칼럼명 타입 조건(not null),st

  PRIMARY KEY ~ ~ );

**INSERT**

- 테이블에 데이터 삽입

  insert into student values(테이블에 맞는 데이터 양식);

**UPDATE**

- 데이터 내용 수정

  update 테이블 set 칼럼 = '값' where 조건;

**DELETE**

- 데이터 삭제

  delete from 테이블 where 조건;

**SELETE**

- 모든 컬럼 조회

  select * from student;

- 필요한 컬럼 조회

  select age, name from student;

