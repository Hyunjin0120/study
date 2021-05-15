## React 기본
### React 화면 렌더링 흐름
* public > index.html : <div id='root'></div>
* src > index.js : id='root'인 div를 찾아 App.js를 렌더링 (ReactDOM.render)
* src > App.js : 화면에 보여줄 컴포넌트 정의

### JSX?
* js 코드 내부에 html이 사용된 형태

### Props 전달
* 부모 컴포넌트(A)에서 자식 컴포넌트(B)로 프로퍼티 전달 시, props라는 object로 모든 프로퍼티를 전달받거나, 아래와 같은 형태로 하나의 프로퍼티만 전달받을 수 있다.
    * A : <B propName="propVal">
    * B : function B({propName}){} 


### Component Life-cycle
<img src="https://user-images.githubusercontent.com/6733004/45586846-2a131180-b938-11e8-9655-c9dd20f74ef5.png" />



## JSX
* 리액트 공식문서를 참조하였습니다. (https://ko.reactjs.org/docs/introducing-jsx.html)

### JSX에 표현식 포함하기
* JSX 안에 중괄호를 이용하여 모든 JS 표현식을 삽입 가능
   ex) 2+2, user(변수), function(user)...
* JSX도 표현식이기 때문에 컴파일 후, JS 객체로 인식됨. 따라서 if나, for문 등 JS 함수 내에서 사용 가능
* 필수는 아니지만, 아래와 같이 괄호로 묶어주는 게 권장됨
 *참고) JSX는 HTML보다 JS에 가깝기 때문에, camelCase 사용
 
 ### JSX vs. 주입공격(XSS)
 * ReactDOM은 JSX에 삽입된 모든 값을 렌더링 전 **이스케이프** 하므로, 명시적으로 작성되지 않은 내용은 주입되지 않음
 *참고) escape - URI에 데이터를 전송할 때, &나 / 등 일부 문자들은 특수한 기능으로 사용되는데, 만일 전달하는 데이터 중 이런 문자가 포함되어 있다면 데이터가 제대로 인식되지 못한다. 따라서 인터넷주소에 사용되는 알파벳, 숫자, 일부 특수문자를 제외한 모든 문자는 유니코드 형식으로 인코딩하여 전달된다.
 
 
