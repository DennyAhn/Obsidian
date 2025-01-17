
데이터베이스를 관리하고 운영하는 소프트웨어를 DBMS(Database Management System)라고 하며다양한 데이터가 저장되어 있는 데이터베이스는 여러 명의 사용자나 응용 프로그램과 공유하고 동시에 접근이 가능하다.

### DBMS 두 가지 유형

### SQL (Structured Query Language)

- **정의**: SQL 데이터베이스는 관계형 데이터베이스 관리 시스템(RDBMS)에서 사용되며, 데이터를 테이블 형태로 저장합니다. 이 테이블들은 행과 열로 구성되며, 데이터 간의 관계를 정의하고 효율적인 검색 및 관리를 가능하게 합니다.
- **특징**:
    - **구조화된 데이터**: SQL 데이터베이스는 엄격한 스키마(제약)에 따라 데이터를 구조화합니다. 이는 데이터의 일관성과 무결성을 보장합니다.
    - **ACID 속성**: 원자성(Atomicity), 일관성(Consistency), 고립성(Isolation), 지속성(Durability)을 보장합니다. 이는 데이터베이스 트랜잭션이 안정적이고 신뢰할 수 있음을 의미합니다.
    - **복잡한 [[쿼리]]**: SQL 언어는 매우 강력하며, 복잡한 쿼리와 다양한 데이터 조작을 지원합니다.
- **예시**: MySQL, PostgreSQL, Oracle, SQL Server 등

### NoSQL (Not Only SQL)

- **정의**: NoSQL 데이터베이스는 비관계형 데이터베이스로, 다양한 데이터 저장 모델(문서, 키-값 쌍, 그래프 등)을 지원합니다. 관계형 모델에 비해 더 유연한 스키마를 제공하며, 수평적 확장성이 뛰어납니다.
- **특징**:
    - **유연한 스키마**: 데이터 구조가 빈번히 변경될 경우에 유리합니다. 스키마 변경 없이 다양한 형태의 데이터를 저장할 수 있습니다.
    - **확장성**: 일반적으로 수평적 확장이 용이하며, 더 많은 서버를 추가하여 처리 능력을 증가 시킬 수 있습니다.
    - **빠른 처리 속도**: 구조화되지 않은 데이터나 대규모 데이터 세트의 처리에 효과적입니다.
- **예시**: MongoDB, Cassandra, Couchbase, Neo4j 등

### SQL과 NoSQL의 주요 차이점

1. **데이터 모델**: SQL은 관계형 모델을, NoSQL은 비관계형 모델(문서, 키-값, 그래프 등)을 사용합니다.
2. **스키마 유연성**: SQL은 엄격한 스키마를 요구하는 반면, NoSQL은 더 유연한 스키마를 제공합니다.
3. **확장성**: SQL 데이터베이스는 수직적 확장(서버의 성능 향상)에 초점을 맞추는 반면, NoSQL 데이터베이스는 수평적 확장(더 많은 서버 추가)에 유리합니다.
4. **트랜잭션**: SQL 데이터베이스는 ACID 속성을 강조하며, 복잡한 트랜잭션 처리에 강점을 보입니다. NoSQL은 대규모 데이터 처리와 분산 환경 에서의 성능에 중점을 둡니다.
5. **쿼리 언어**: SQL 데이터베이스는 SQL 쿼리 언어를 사용하여 데이터에 접근합니다. NoSQL 데이터베이스는 다양한 쿼리 방식을 제공하지만, SQL만큼 표준화 되거나 복잡한 쿼리를 지원하지 않을 수 있습니다.