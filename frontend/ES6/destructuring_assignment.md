## 구조분해 할당 (Destructuring assignment)
* 노마드 코더의 React 무비앱 클론코딩 중, ES6 문법인 구조분해 할당에 대한 내용을 추가적으로 정리해보았다.
* 참고 : https://ko.javascript.info/destructuring-assignment


### 언제 사용하면 좋을까?
>> 함수에 객체(키-밸류 집합) 혹은 배열(컬렉션에 데이터를 순서대로 저장)의 일부 데이터만 전달하고자 할 때!

## 사용법
1) 배열 분해하기
>> let arr = ["lim", "hyunjin"];
>> let [lastName, firstName] = arr;
>> alert(firstName); //hyunjin

2) 쉼표로 특정 요소 무시하기
>> let [first, , third] = ["first", "second", "third"];
>> alert(third); //third

3) 모든 이터러블에 적용 가능
>> 문자열, set 등 모든 반복 가능한 객체에 적용 가능