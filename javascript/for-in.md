# 객체 순환에 사용되는 for-in문

## for-in 문

**for-in문이란?**

- 객체의 모든 프로퍼티를 순회하여 열거한다
- `for-in`문은 객체의 프로퍼티 개수만큼 순회하며 `for-in`문 변수 선언문에서 선언한 변수에 프로퍼티 키를 할당함
- 배열은 순서보장이 중요하므로 `for-in`문 대신에 `for-of`문으로 순환해야한다

```js
for (변수선언문 in 객체) {...}
```

```js
const person = {
  name: "seju",
  age: 26,
};

for (const key in person) {
  console.log(key); // name, age
  console.log(person[key]); // 'seju', 'age'
}
```

### 더 정확한 표현은 프로포타입 체인 상에 존재하는 모든 프로토타입의 프로퍼티 중에서 프로퍼티 어트리뷰트 `[[Enumerable]]` 값이 `true`인 프로퍼티만을 순회하며 열거

- 아래코드에서 `__proto__`로 선언한 키와 `Symbol`객체는 순회하지 ❌
  - 또한 `toString`등 상속받은 프로퍼티 또한 열거하지 않는다
    - [[Enumerable]] 값이 `false`이므로

```js
const person = {
  name: "seju",
  age: 26,
  __proto__ : {address : 'seoul'}
  [sym] : 10
};

for (const key in person) {
  console.log(key); // name, age
  console.log(person[key]); // 'seju', 'age'
}
```
