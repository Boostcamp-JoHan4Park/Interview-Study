# Database  

## Questions  
* [DBMS를 정의하세요.](#1)

* [RDBMS를 정의하고 장점에 대해 설명하세요.](#2)

* [key 정리](#3)

  - Candidate Key
  - Primary Key
  - Alternate Key
  - Super Key
  - Foreign Key

* [SQL Join (join이란? join 종류)](#4)

  



## Answers
### #1

DBMS를 알기 위해서는 DB를 먼저 정의해야 된다고 생각합니다. 데이터베이스는 데이터에서 중복된 데이터를 없애고, 효율적인 처리를 할 수 있도록 **관리되는 데이터의 집합**입니다. DBMS는 이러한 **DB를 정의, 조작, 제어**를 하여 데이터 베이스를 **공유할 수 있도록 관리해주는 소프트웨어**입니다.



Reference

https://myjamong.tistory.com/165

https://it-earth.tistory.com/102



### #2

행과 열로 저장되어 있어 탐색, 정렬, 질의 시에 **빠르다**는 장점이 있습니다.

But NoSQL 보다 적은 데이터를 저장, 처리할 수 있다는 단점이 있습니다.



### #3

Primary key : 테이블 식별자 역할로 테이블에서 하나만 설정할 수 있는 키

unique key : 테이블 내에 항상 유일해야 하는 값, 중복 허용 X

foreign key : 다른 테이블의 기본키를 참조하는 키

super key : 테이블에서 각 행을 유일하게 식별할 수 있는 하나 또는 그 이상의 속성들의 집합

candidate key : 각 행을 유일하게 식별할 수 있는 최소한의 속성들의 집합

alternate key : 후보키가 두개 이상일 경우 그 중에서 어느 하나를 기본키로 지정하고 남은 후보키



ref

https://jerryjerryjerry.tistory.com/49



### #4

두 개 이상의 테이블에 대해서 결합할 때 사용하는 것이 조인이다. join하는 방법에 따라 Inner join, left, right join 등이 있습니다.