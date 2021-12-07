## Redis 
오늘은 NoSql 의 한 종류인 Redis에 대해 알아보려한다. 평소 업무에는 RDBMS(관계형 DB)인 Oracle Sql만 사용하여 NoSql을 접할 기회가 없었다. Cache 서버로 활용하기 적합한 Redis를 공부하고,
이후 간단한 프로젝트에 활용할 계획이다.

### Redis란?
1. NoSql
  - RDBMS와 대비되는 NoSql(비관계형 데이터베이스)의 일종
  - Document-oriented DB인 MongoDB, key-value 형식의 Redis, DynamoDB 등이 대표적
  - 대량의 비정형데이터 저장 가능
2. Redis의 특징
  - 영구적 in-memory DB : 명시적으로 삭제하거나 만료기간을 설정하지 않는 이상 메모리에 데이터 영속
  - key-value 형식으로 데이터 저장 : value로 다양한 타입 지원 (String, List, Set, Sorted set, Hash 등)
  - 싱글 쓰레드 (Single Thread)로 수행 : 한 번에 한 개 명령어만 실행하기에, "keys"나 "flushall" 같은 실행 대상을 전수처리하는 명령어는 지양(속도저하)
  - Replication 전략 : Master - Slave 로 여러 서버를 구성하여 가용성 증진
