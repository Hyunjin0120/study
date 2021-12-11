## Redis 
오늘은 NoSql 의 한 종류인 Redis에 대해 알아보려한다. 대략의 개념, 그리고 Cache 서버로 활용하기 적합하다는 것만 알고 실제로써볼 기회는 없었던 Redis. 간단히 정리해보고, 이후 개인 프로젝트에 활용할 계획이다.

### NoSql 의 일종
  - RDBMS와 대비되는 NoSql(비관계형 데이터베이스)
  - 대량의 비정형데이터 저장 가능
  - Document-oriented DB인 MongoDB, key-value 형식의 Redis, DynamoDB 등이 대표적
  
### Redis의 특징
  - 영구적 in-memory DB : 명시적으로 삭제하거나 만료기간을 설정하지 않는 이상 메모리에 데이터 영속시킬 수 있음
  - key-value 형식으로 데이터 저장 : value로 다양한 타입 지원 (String, List, Set, Sorted set, Hash 등)
  - Single Thread 수행 : 한 번에 한 개 명령어만 실행하기에, 운영 환경에서 "keys"나 "flushall" 같이, 실행 대상을 전수처리하는 명령어 지양(속도저하)
  - Replication 전략 : Master - Slave 로 여러 캐시 서버를 구성하여 가용성 증진 도모

### Redis의 활용 사례
  - 댓글 '좋아요' 데이터 저장 : RDBMS에서 Unique로 처리하던 것을 Redis의 Set으로 처리 가능
  - 최근 검색 목록 : RDBMS에서 중복 제거/사용자별 총 데이터 개수 확인/오래된 검색어 삭제 세 과정으로 이루어질 작업을 Redis의 Sorted Set으로 처리 가능<br/>* 참고자료 : [Redis 구조 실제 활용 사례](https://ozofweird.tistory.com/entry/Redis-Redis-%EA%B5%AC%EC%A1%B0-%EC%8B%A4%EC%A0%9C-%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80)

### Redis Pub/Sub
https://brunch.co.kr/@springboot/374
