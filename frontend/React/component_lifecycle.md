## React Component Lifecycle
* 노마드코더의 리액트 클론코딩 강의(https://nomadcoders.co/react-fundamentals/lectures/1555)를 들으며 공부 중이었는데, 업무가 너무 바빠 거의 두 달간 야근과 주말근무를 피할 수 없었다... 오랜만에 리액트 공부를 하려니 새롭다. 오늘은 리액트 컴포넌트의 라이프사이클에 대해 알아보려 한다.
### 참고자료
* https://dev.to/jaylcaetano/react-component-lifecycle-2npl
* https://velog.io/@cyranocoding/React-Life-Cycle-%EC%8B%9C%EB%A6%AC%EC%A6%88Mount-%ED%8E%B8


### Lifecycle의 대분류
 <img src="https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/" />
 
 1) Mounting : 컴포넌트의 생성
 2) Updating : 새로운 props 혹은 상태 변화
 3) Unmounting : 컴포넌트 삭제

 ### Mount
 1) constructor()
    - 선언 필수 X. 선언 시 super(props) 반드시 호출
    - 아직 mount 되기 전이기 때문에 state에 관한 내용 작성 X (비동기 작업은 componentDidMount에서)
 2) render()
    - JSX로 작성한 엘리먼트를 retunr
    - 해당 엘리먼트들이 virtual DOM에 mount된 후, 실제 DOM에 업데이트됨
    - 순수함수, 즉 항상 같은 input에 대하여 같은 output이 나와야 함
    - 내부에 setState 작업 X. state 변경되면 다시 render 되고, 그럼 다시 setState 되고... 무한루프
 3) componentDidMount()
    - 엘리먼트가 DOM에 mount 된 직후 실행
    - DOM 노드 확인하고 초기화해야 할 때 사용

### Update
 1) componentDidUpdate
    - 상위 component로부터 갱신된 props를 받거나, state가 업데이트된 경우
    - update 후 render 완료된 직후 실행됨
### Unmount
 1) componentWillUnmount
    - component가 DOM에서 제거될 때 실행됨
    - component 내의 이벤트를 해제할 때 사용