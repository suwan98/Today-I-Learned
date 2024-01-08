# JavaScript Iterable

## 이터러블이란?

**이터러블 프로포콜을 준수한 객체**

- `Symbol.iterator`를 프로퍼티 키로 사용한 메서드를 직접 구현하거나 프로토타입 체인을 통해 상속받은 객체를 뜻한다.

## 이터러블 프로토콜이란?

- 순회가능한 데이터 자료구조를 만들기 위해 ECMAScript 사양에 정의해 미리 약속한 규칙
- ES6 이전의 순회 가능한 데이터 컬렉션(배열,문자열,유사배열객체, DOM 콜렉션)

  - 통일된 규약없이 각자 나람의 자료구조를 가지고 `for` 문`for-in`문 `forEach` 메서드등을 통해 다양한 방법으로 순회할 수 있었음.

    **그러나 ES6 이후에는 순회가능한 데이터 컬렉션을 이터레이션 프로토콜을 준수하는 이터러블로 통일
    `for-of`문/스프레드문법/배열 디스트럭쳐링 할당의 대상으로 사용할 수 있도록 일원화**

## 자바스크립트에서 제공하는 빌트인 이터러블 객체들

자바스크립트는 이터러블 프로포콜을 준수한 객체인 빌트인 이터러블을 제공하고 있다.

| 빌트인 이터러블 | Symbol.iterator 메서드                    |
| --------------- | ----------------------------------------- |
| Array           | Array.prototype[Symbol.iterator]          |
| String          | String.prototype[Symbol.iterator]         |
| Map             | Map.prototype[Symbol.iterator]            |
| Set             | Set.prototype[Symbol.iterator]            |
| TypedArray      | TypedArray.prototype[Symbol.iterator]     |
| arguments       | arguments[Symbol.iterator]                |
| DOMCollection   | HTMLCollection.prototype[Symbol.iterator] |
| NodeList        | NodeList.prototype[Symbol.iterator]       |
