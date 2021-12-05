## Spring Annotation
평소 관성적으로 사용하던 @Controller나 @Repository 같은 스프링 어노테이션들에 대해 조금 더 깊이 알아보고자 한다. 단순히 스프링에서 편하게 기능을 사용할 수 있게 해주는 것들로 알았는데, 이번에 AOP에 대해 공부하면서 어노테이션의 동작 원리가 궁금해졌다. 

### Annotation?
정의는 말 그대로 '주석'이라는 의미. 실제로 ctrl+space 로 타고 들어가서 보면 어노테이션 이름으로 정의된 인터페이스와 긴 설명을 볼 수 있다. 추가적인 기능을 제공하는 메타데이터의 일종이다. 

### 어노테이션의 기능
- 컴파일러에 코드 작성 문법 에러를 체크하도록 정보 제공(RetentionPolicy.SOURCE)
- 컴파일 시 특정 바이트코드를 생성하도록 정보 제공(RetentionPolicy.CLASS)
- 런타임 시 특정 기능 수행하도록 정보 제공(RetentionPolicy.RUNTIME)
   *뒤에 붙은 RetentionPolicy가 무엇인지는 아래 참고

### 어노테이션 정의하기
- Target : 어노테이션 적용 대상 (ex. Class, Method, Module, Package ...)
- Retention : 어노테이션 유지 범위 (ex. SOURCE, CLASS, RUNTIME)
- Annotation Name : 인터페이스로 정의된 어노테이션 이름

### 어노테이션 사용 방법
1. 어노테이션 인터페이스 정의
2. Aspect 정의 및 해당 어노테이션을 Target으로 지정
3. 어노테이션에 정의된 Target(Class, Method, Module...)에 어노테이션 적용

<hr/>

### Comment
생각없이 사용해오던 스프링 어노테이션이었지만, 이제 정의하고 활용하는 방법을 얕게나마 알게 되었다! 추가로, RetentionPolicy에 대하여 잘 설명한 [자료](https://jeong-pro.tistory.com/234)가 있어 추가한다. 
