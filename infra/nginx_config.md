## Nginx 설정 방법
* 회사에서 nginx 설정을 조금 만져본 적이 있는데, 그때 관련해서 이것저것 공부한 적이 있다. 
* 참고 : https://12bme.tistory.com/366
** try_files 설정

### 기본 설정
1. nginx.conf : 설정파일로, 보통 /etc/nginx/* 에 위치
    * 로그파일은 /var/log/nginx/* 에 위치
2. 모듈 구조 : 엔진엑스는 모듈 구조로 작동하기에 각 모듈이 특정 지시어 묶음 형태로 제공됨. 모듈이 제공하는 지시어는 해당 모듈의 블록 내에서만 사용 가능.
    * Core module : 기본 지시어 포함
3. 구조와 인클루드
    * include : 특정 (환경설정) 파일 포함하기
    ```
    include mime.types;
    ```
    * 설정 파일의 종류
        - nginx.conf : 애플리케이션의 기본 환경 설정
        - mime.types :  파일 확장명과 MIME 타입 목록
        - fastcgi.conf : FastCGI 관련 환경 설정
        - proxy.conf : 프록시 관련 환경 설정
        - sites.conf : 엔진엑스에 의해 서비스되는 가상 호스트 웹사이트의 환경 설정. 도메인마다 파일을 분리해서 만들 것을 권장.
4. http 블록과 server 블록
    * server 블록 : 하나의 가상 호스트를 구성.

5. 기본 모듈 지시어
    * 코어 모듈(Core module) : 프로세스 관리, 보안 등의 필수적 기능 및 지시어
    * 이벤트 모듈(Events module) : 네트워크 기능의 내부 작동 방식
    * 환경 설정 모듈(Configuration module) : include 기능 제공

6. 모듈별 설정 (이어서)