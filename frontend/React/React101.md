### React 화면 렌더링 흐름
* public > index.html : <div id='root'></div>
* src > index.js : id='root'인 div를 찾아 App.js를 렌더링 (ReactDOM.render)
* src > App.js : 화면에 보여줄 컴포넌트 정의

### JSX
* js 코드 내부에 html이 사용된 형태

### Props 전달
* 부모 컴포넌트(A)에서 자식 컴포넌트(B)로 프로퍼티 전달 시, props라는 object로 모든 프로퍼티를 전달받거나, 아래와 같은 형태로 하나의 프로퍼티만 전달받을 수 있다.
    * A : <B propName="propVal">
    * B : function B({propName}){} 


### Component Life-cycle
<img src="https://user-images.githubusercontent.com/6733004/45586846-2a131180-b938-11e8-9655-c9dd20f74ef5.png" />
