# Scope

## 자바스크립트에서의 Scope 개념

자바스크립트에서 스코프를 구분하면 3가지로 나눌 수 있다

- **전역스코프(Global Scrope)**
  - 코드 **어디에서든 참조** 가능하다

- **지역스코프(Local scope or Function-level scope)**
  - 함수 코드 블록이 만든 스코프, **함수 자신과 하위 함수에서만 참조** 할 수 있다.

- **블록스코프(Block scope)**
  - 중활호로 묶인 코드 블록 내에서만 변수가 유효한 스코프

  또한 모든 변수는 스코프를 갖는데, 변수의 관점에서 스코프를 구분하면 2가지로 나눌 수 있다

<hr />

- **전역변수(Global Scope)**
  - 전역에서 선언된 변수이며, **어디서든 참조** 가능

- **지역변수(Local Scope)**
  - **지역(함수)내에서 선언된 변수**, 그 지역과 그 지역의 하부지역에서만 참조가능

```js
const name = 'suwan' //전역스코프이자, 전역변수

// sayName()은 지역스코프
function sayName(){
    const name = 'seju' //함수내에서 name은 지역스코프에 속하며 지역변수
    console.log(name)
    //for문 블록스코프
    for(let i =0; i<5; i++){
        console.log(i)
    }
}

sayName() //seju
console.log(name) // suwan

```

