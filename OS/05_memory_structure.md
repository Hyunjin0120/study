## 메모리 구조
* 프로세스 실행 시 메모리에 code, data, stack 으로 이뤄진 process address 가 올라간다고 알고 있다. 하지만 heap 에 대해서는 잘 알지 못해 오늘 그 개념을 보고자 한다.
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcDYB89%2FbtqCynYFKon%2FS6HkTy9CkrA87LEjTcDDl1%2Fimg.png)

1. 메모리 구조의 기초
* 코드 영역 : 텍스트 영역. CPU가 실행할 프로그램의 코드
* 데이터 영역 : 메서드 영역. 전역변수, 정적 변수. JVM이 main 메서드 가장 먼저 호출. 프로그램 시작 시 할당&종료 시 소멸
* 힙 영역 : 사용자의 동적 할당 / 런타임 시 크기 결정됨. 사용자가 직접 관리하는 메모리 영역. new 연산자로 메모리 할당하는 것. Garbage Collector나 JVM 에 의해 메모리 해제될 때까지 유지됨. 
* 스택 영역 : 지역변수, 매개변수 / 컴파일 시 크기 결정됨. 함수가 호출되면 할당됨

2. 힙 vs. 스택
* 원시 타입 이외의 타입은 모두 참조변수
* 참조변수의 경우 스택 영역에 저장하면 비효율적이라 힙 영역에 값이 저장되고 스택에는 주소값만 저장

### 정리
지역변수가 저장되는 스택 영역, 참조변수의 진짜 값이 저장되는 힙 영역. 간단하다!
