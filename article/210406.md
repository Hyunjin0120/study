# Kafka와 Pub/Sub 모델
### 참고자료
* https://kchanguk.tistory.com/75
* https://kchanguk.tistory.com/78?category=885723
* https://m.blog.naver.com/PostView.nhn?blogId=edusns1&logNo=221069285964&proxyReferer=https:%2F%2Fwww.google.co.kr%2F
* https://blog.voidmainvoid.net/265


## Pub/Sub 모델
### Pub/Sub 모델
* Publish/Subscriber의 줄임말로, 메시지 기반의 미들웨어 시스템을 뜻함
* pub과 sub는 서로를 알지 못하고, 메시지를 카테고리화한 토픽에 대한 정보만 알고 있음

### 미들웨어란?
* OS와 응용 프로그램 사이에 존재하며, 응용 프로그램에게 데이터관리와 통신 같은 공통 기능을 제공하는 소프트웨어
* 데이터 관리, 애플리케이션 서비스(WAS), 메시징, 인증 및 API 관리 등
* SOAP, 웹서비스, REST, JSON 등과 같은 메시징 프레임워크를 사용하여 통신

### Message Filtering
* Topic-based System : pub이 메세지의 토픽을 정의하고 해당 토픽으로 메시지를 전송. 그러면 sub는 자신이 원하는 토픽의 메세지만 전송받음
* Content-based System : sub이 원하는 토픽을 정의하면, pub으로부터 해당 토픽의 메시지만 전송됨
* Hybrid System : pub은 메시지의 토픽을 정하고 각 토픽에 대한 메시지를 전송. sub는 그중 자신이 원하는 토픽에 대한 메시지만 받음

### Pub/Sub 모델의 장점
* Loosely coupled : 미들웨어를 통해 pub - sub 간의 연결 약화. 기존에는 서로 system topology에 대한 제약이 많았음
* Scalable : 설치 비용 적고 연결이 약해 확장성이 좋음

### Pub/Sub 모델의 단점
* e2e 시스템의 강점 상실 : 기존에는 전송부와 수신부가 직접 통신했기에 목적지까지 메시지가 확실히 전송됨. 그러나 미들웨어를 통하면 전달 실패할 수도 있음.

<hr/>

## Kafka
### 데이터 파이프라인이란?
* 데이터를 한 시스템에서 다른 시스템으로 옮기는 작업으로, ETL(Extract, Transform, Load)을 포함하는 개념

### Apache Kafka
* 대용량 실시간 로그 처리에 특화된 Pub/Sub 모델 기반의 메시징 시스템
* 구성요소
   * Producer : 데이터 발생시키고 Kafka Cluster에 적재하는 프로세스
   * Kafka Cluster : 카프카 서버로 이뤄진 클러스터
   * Broker : 카프카 서버
   * Zookeeper : 분산 코디네이션 시스템. 각 Broker마다 존재하며, 여러 broker들을 하나의 Cluster로 묶고 leader를 발탁하는 방식을 제공
   * Leader : 모든 읽기, 쓰기 연산을 담당
   * Follower : 단순히 리더의 데이터를 복사
   * Topic : Kafka Cluster에서 데이터를 관리하는 기준이 되는 개념. 각 Topic은 한 개 이상의 Partition(데이터 분산처리의 단위)으로 구성됨

* 특징
    * 데이터 영속성 : 파일 시스템에 메시지 저장
    * Pull 방식 : 기존 메시징 시스템은 broker가 consumer에게 메시지를 push하지만, 카프카는 consumer가 broker로부터 메시지를 pull 해가는 방식
    * bath 방식 : 다수의 메시지를 batch 형태로 broker에게 한번에 전달하여 TCP/IP 라운드 트립 횟수 감소
