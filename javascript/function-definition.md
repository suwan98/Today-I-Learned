✏️  **함수 정의**


함수 정의하는 방식에는 세가지 존재

- 함수 선언문
- 함수 표현식
- Function 생성자 함수

<hr/>
<br />
✏️ 함수 선언문 <br/>
<br/>
정의한 함수는 function 키워드와 아래의 내용으로 구성

- 함수명 : 함수 선언문으로 작성 시 함수명은 생략 **X**
- 매개변수 목록 : 0개 이상의 목록으로 괄호를 감싸고 콤마로 구분
- 함수 몸체 : 함수가 호출되었을 때 실행되는 문들의 집합 중괄호로 문을감싼 후 `return` 문으로 결과값을 반환 할 수 있다
  
```javascript
// 함수 선언문
function square(number) {
  return number * number;
}
```

<br/>
✏️ 함수 표현식 <br/>

함수는  **객체타입의 값**

따라서 함수는 **값처럼 변수에 할당 할 수 도 있고 프로퍼티의 값이 될 수도 있으며 배열의 요소가 될 수도 있다**

이처럼 값의 성질을 갖는 객체를 **일급객체**라 명명(=함수)

함수는 일급 객체이므로 함수 리터럴로 생성한 함수 객체를 변수에 할당 가능

이러한 함수 정의 방식을 함수 표현식이라고 한다

```jsx
// 함수 표현식
var square = function(number) {
  return number * number;
};
```

함수 표현식 방식에선 정의한 함수는 생략할 수 있으며

이를 **익명함수**라 함

함수 표현식 에서는 함수명을 생략하는 것이 일반적
```jsx
// 기명 함수 표현식(named function expression)
var foo = function multiply(a, b) {
  return a * b;
};

// 익명 함수 표현식(anonymous function expression)
var bar = function(a, b) {
  return a * b;
};

console.log(foo(10, 5)); // 50
console.log(multiply(10, 5)); // Uncaught ReferenceError: multiply is not defined
```

함수는 앞에 말했듣이 변수에 할당이 가능한데,

해당 변수는 함수명이 아니라 **할당된 변수를 가리키는 참조값**을 **저장**한다

따라서 호출 시 함수명이아니라 변수명을 사용해야한다!

```jsx
var foo = function(a, b) {
  return a * b;
};

var bar = foo;

console.log(foo(10, 10)); // 100
console.log(bar(10, 10)); // 100
```
✏️ Function 생성자 함수

함수 선언문과 함수 표현식은 모두 함수 리터럴 방식으로 함수를 정의하는데 이것은 결국 내장 함수 Function 생성자 함수로 함수를 생성하는 것을 단순화시킨 **short-hand(축약법)**

```jsx
var square = new Function('number', 'return number * number');
console.log(square(10)); // 100
```
일반적으로 Function 생성자 함수로 생성하는 방식은 일반적으로 사용 X

<br />
<br />
<hr />
✏️ 화살표 함수 <br/><br/>
함수표현식보다 더 간결한 문법으로 함수를 만들수 있다

`let func = (args1,args2) = > expression`

인자 args1,args2를 받는 함수가 만들어진다

즉 아래 함수의 축약 버전

```jsx
let func = function(arg1, arg2, ...argN) {
  return expression;
};
```

그런데 평가해야 할 표현식이나 구문이 여러 개일 경우?🤔 <br/>
표현식 내부에 중괄호를 삽입 후 `return`을 사용해서 결괏값을 명시적으로 반환해줘야한다

```jsx
let sum = (a, b) => {  // 중괄호는 본문 여러 줄로 구성되어 있음을 알려줍니다.
  let result = a + b;
  return result; // 중괄호를 사용했다면, return 지시자로 결괏값을 반환해주어야 합니다.
};

alert( sum(1, 2) ); // 3
```