# OAuth2.0
## OAuth2.0 의 동작방식
### 주체
* Resource Owner(User) : RS에 계정을 가진, Client의 서비스를 이용하려는 유저
* Client : OAuth를 통해 RS의 기능(API)을 사용하려는 애플리케이션 혹은 웹 서비스
* Resource Server : OAuth를 사용하는, Open API를 제공하는 서버
* Authorization Server : OAuth 인증을 처리해주는 서버

### 흐름
1) Client  RS : OAuth 사용 요청
2) RS  Client : Client ID와 secret 부여. 제공할 정보에 대한 scope도 설정 가능.
3) User  Client : RS가 제공하는 자원 사용하고자 RS의 OAuth 인증 클릭. Client에서 AS가 제공하는 로그인 페이지로 리다이렉트됨
4) AS  User(Client) : 로그인 성공 시 Authorization Code 발급. 리다이렉트 URI로 해당 code가 Client에 전달됨
5) Client  AS : Authorization Code를 가지고 AS에게 Access Token 요청
6) AS  Client : Access Token과 Refresh Token 발급
7) User  Client : 인증 완료 및 로그인 성공 후, Client에게 RS의 API 서비스 요청
8) Client  RS : Access Token으로 API 호출
9) RS  Client : Authorization Code 검증 및 서비스 제공
10) Client  User : 서비스 제공
