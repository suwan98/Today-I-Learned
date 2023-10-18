# 렉시컬 스코프

## 동적스코프 / 렉시컬 스코프 개요

**아래 코드에서의 결과는 `bar`함수의 상위 스코프가 무엇인지에 따라 결정된다**

- 함수를 어디에서 호출했는지에 따라 상위 스코프가 결정
- 함수를 어디에서 정의했는지에 따라 상위 스코프가 결정

```js
var x = 1; //전역변수

function foo() {
  //전역스코프 foo
  var x = 10;
  bar();
}

function bar() {
  //전역스코프 bar
  console.log(x);
}

foo(); // 1
bar(); // 1
```

**여기서 첫번째(함수를 어디서 호출했는지) 방식이 동적스코프**

- 함수를 정의하는 시점에는 함수가 어디서 호출될지 알 수 ❌
- 함수가 호출되는 시점에 동적으로 상위스코프를 결정해야하므로 **동적스코프**라 한다

**두번째 방식(함수를 어디서 정의했는지) 방식이 정적스코프 즉, 렉시컬스코프**

- 자바스크립트는 함수가 호출된 위치는 상위 스코프 결정에 어떠한 영향도 주지 ❌
  - 즉, 함수의 상위스코프는 **언제나 자신이 정의된 스코프**이다

## 자바스크립트는 정적 스코프(=렉시컬 스코프(Lexical Scope))이다

-

### 동적스코프/정적스코프 비교

**동적스코프 코드 얘시**

- `printName` 함수 내에서 `personName` 변수를 선언 후 `local jake`로 초기화
- `getPersonName` 함수를 호출 해 `name` 변수에 할당
- 그러나 `getPersonName` 함수 내 사용 된 `${personName}`은 정적으로 작성된 템플릿 리터럴
- 따라서 `${personName}`은 현재 스코프에서 찾을 수 없으므로 에러가 발생함

```js
function getPersonName() {
  return `my name is ${personName}`;
}

function printName() {
  let personName = "local jake"; // 지역 변수
  let name = getPersonName();
  console.log(name);
  return name;
}

printName();
```

**정적스코프 코드 예시**

- 런타임을 참조하지 않고, 정적으로 블록별 스코프 체인을 따라 전역 스코프까지 올라가 변수의 이름을 찾아낸다
  - 아래 코드의 경우엔 `getPersonName` 함수 내부에서 찾을 수 있다.

```js
function getPersonName() {
  let personName = "local jake"; // 지역 변수
  return `my name is ${personName}`;
}

function printName() {
  let name = getPersonName();
  console.log(name);
  return name;
}

printName();
```
