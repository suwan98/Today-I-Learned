# 옵셔널 체이닝 '?.'

## 옵셔널 체이닝이란?

- 자바스크립트에서속성값을 읽거나 메서드를 호출시, 해당 속성이나 메서드가 존재하지 않더라도 에러가 발생하지 않게 해주는 안전한 방법을 제공한다.
- 옵셔널 체이닝을 사용 시 중첩된 객체의 속성에 접근시 그 중 하나라도 정의되지 않았다면 `undefined`를 반환하고, 더 이상의 실행을 멈춘다.
- 리액트에선 컴포넌트가 예상치못한 `undefeind`나 `null`값으로 인해 런타임에러를 발생시키는것을 방지할 수 있게된다.

<br />

## 기본 사용법

```js
const person = {
  name: "John",
  address: {
    street: "123 Main St",
    city: "Anytown",
  },
};

// 옵셔널 체이닝 사용
console.log(person.address?.city); // "Anytown"
console.log(person.address?.postcode); // undefined

// 배열에 대한 옵셔널 체이닝
const people = [{name: "John"}];
console.log(people[1]?.name); // undefined

// 함수 호출에 대한 옵셔널 체이닝
const object = {
  myFunction: () => console.log("Hello World!"),
};

object.myFunction?.(); // "Hello World!"
object.nonExistentMethod?.(); // 아무 일도 일어나지 않음 (undefined 반환)
```
