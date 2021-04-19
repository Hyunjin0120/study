# SSL,SSH와 SFTP
* 회사에서 젠킨스를 통한 자동 배포를 도입하기 이전에는, SFTP를 이용한 자체 솔루션을 통해서 직접 서버에 붙어 파일을 전송하는 식으로 배포를 했다. 
* 이 과정에서 SFTP를 이용하면서 단순히 보안이 강화된 파일 전송 기능으로만 생각했다.
* 그런데 최근 docker를 공부하며, SSL 과 같이 보안 관련하여 막히는 부분이 있어 관련 개념을 제대로 알아봐야겠다고 생각했다.

## SSL
* 참고
* https://heodolf.tistory.com/94
* https://engineering.linecorp.com/ko/blog/best-practices-to-secure-your-ssl-tls/

### 개요
* SSL (Secure Sockets Layer) : 서버 - 클라이언트 간 교환되는 데이터를 암호화하는 기술로, 대칭키 기반. HTTPS가 대표적.
* TLS (Transport Sockets Later) : SSL 3.0 업그레이트 버전이 TLS 1.0.

### 로컬에서 TLS 이용하기
* 목표 : mediasoup demo를 위한 TLS 인증서 생성하기
* 참고 : https://m.blog.naver.com/alice_k106/221468341565 (내 입장에서 가장 이해가 쉽게 되는 TLS 설명글이다!)
1) ubuntu_ms:base 이미지 위에 letsencrypt 설치
2) 
