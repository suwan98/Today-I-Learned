# Function.prototype.call() 메서드

**call() 메소드는 주어진 this 값 및 각각 전달된 인수와 함께 함수를 호출**

- 먼저 일반 함수에서의 `this`는 window를 가르킨다.

```jsx
func.call(thisArg[, arg1[, arg2[, ...]]])
```

- `thisArg`: func 호출에 제공되는 `this`의 값
- `arg1, arg2, ...`: `func`이 호출되어야 하는 인수

### 코드로 알아보기

`call`을 이용하여 `person2의` 함수를 호출하고 있지만 `call` 메소드 첫 번째 매개변수에 `person1을` 넣어주고 있기 때문에 `this는` `person2가` 아닌 `person1`을 가리키게 된다.

```js
let person1 = {
  name: "Jo",
};

let person2 = {
  name: "Kim",
  study: function () {
    console.log(this.name + "이/가 공부를 하고 있습니다.");
  },
};

person2.study(); // Kim이/가 공부를 하고 있습니다.

// call()
person2.study.call(person1); // Jo이/가 공부를 하고 있습니다.
```
