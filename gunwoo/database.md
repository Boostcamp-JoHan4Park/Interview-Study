# Database  

## Questions  
* [DBMS를 정의하세요.](#1)
* [RDBMS를 정의하고 장점에 대해 설명하세요.](#2)

## Answers
### #1

- 데이터베이스 관리시스템의 줄임말로 데이터 베이스 구축을 위한 기능들을 제공하고, 추가적으로 효율적으로 데이터를 검색하고 저장하는 기능을 제공합니다. 이 외에도 응용프로그램들이 데이터베이스에 접근할 수 있는 인터페이스를 제공한다거나, 사용자 권한에 따른 보안, 장애 복구 기능을 포함하고 있습니다.

- DBMS는 데이터베이스 관리시스템의 줄임말
- 데이터베이스 구축을 위한 기능들을 제공하고, 효율적으로 데이터를 검색하고 저장하는 기능을 제공
- 응용프로그램들이 데이터베이스에 접근할 수 있는 인터페이스를 제공
- 사용자 권한에 따른 보안성 유지 기능, 장애 복구 기능 제공

- APPENDIX 유명 DBMS
    - 오라클 
        - DBMS 시장의 선두주자
    - MySQL
        - 오픈소스로 공개되어 무료버젼이 많이 쓰임
        - 기업에서도 많이 애용
        - php와 호환이 좋음
    - MariaDB 
        - MySQL이 오라클에 인수된 이후, MySQL 기술진이 오라클을 나와서 개발
        - MySQL 5.5 버전을 기반으로 개발하여 MySQL과 호환이 됨
    - MongoDB
        - NoSQL DBMS
        - RDBMS가 아니어서 SQL을 사용하지 않음

### #2
관계형 데이터 모델에 베이스를 둔 DBMS로 명확하게 정의된 스키마를 사용하고, 데이터 무결성을 보장합니다. NoSQL과는 다르게 각 데이터를 중복업이 한번만 저장하는 장점을 가지고 있습니다.

<!-- 
정규화를 통해 데이터 중복을 최소화하고, NoSQL과 달리 ACID를 보장합니다


- 관계형 데이터 모델에 베이스를 둔 DBMS
- 정규화를 통해 데이터 중복성을 최소화하고, ACID를 보장함
- 업데이트 할때 NoSQL에 비해 빠름

<br>

- 명확하게 정의된 스키마, 데이터 무결성 보장
- 관계는 각 데이터를 중복없이 한번만 저장 -->

- APPENDIX
    - ACID
        - 원자성(Atomicity)
            - 트랜잭션 작업이 부분적으로 실행되거나 중단되지 않는것
        - 일관성(Consistency)
            - 트랜잭션이 성공적으로 완료되면 일관적 DB 상태를 유지
            - 금액의 데이터 타입이 정수형이면 트랜잭션 이후에도 정수형이어야함
        - 독립성(Isolation)
            - 트랜잭션
        - 지속성(Durability)
            - 성공적으로 수행된 트랜잭션은 영원히 반영