## 스키마란?
* 최근 Nest.js를 공부하며, TypeORM(TS, ES5/6/7 용 ORM)을 알게 되었다. TypeORM의 migration 기능을 보던 중, 데이터베이스 스키마가 무엇인지 정확히 정리하고자 글을 쓴다. 
* 지금은 대략 'DB의 구조와 제약조건 등에 대한 명세'로만 알고 있다. migration을 통해 DB의 어떤 것들이 변화하는 것인지 공부해보려 한다.

## 스키마 개요
* 속성(attribute = column)과, 여러 속성이 모여 만들어진 개체(entity), 그리고 개체들 간의 관계(relation)에 대한 정의 
