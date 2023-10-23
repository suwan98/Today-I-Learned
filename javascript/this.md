# this와 동적 바인딩

## this 키워드

**객체와 `this`**

- 상태를 나타내는 **프로퍼티**와 해당 프로퍼티들의 동작을 나타내는 **메서드**
  - 메서드는 프로퍼티를 참조하고 변경할 수 있어야 한다
  - 메서드가 자신이 속한 객체의 프로퍼티를 참조하려면 **먼저 자신이 속한 객체를 가르키는 식별자를 참조할 수 있어야 한다**
    - `this`가 필요한 이유

<br />

### 객체 리터럴로 생성한 객체의 프로퍼티 참조 방식

**메서드 내부에서 메서드 자신이 속한 객체를 가리키며 식별자로 재귀적으로 참조할 수 있다**

```js
const literalCircle = {
  radius: 5,
  getDimeter() {
    // 자신이 속한 객체 literalCircle을 재귀적으로 참조 가능
    return 2 * literalCircle.radius;
  },
};

console.log(literalCircle.getDimeter(2));
```

**그러나 재귀적으로 참조하는 방식은 일반적인 방식이 ❌**

<br />

### 생성자 함수로 인스턴스를 생성하는 경우 프로퍼티 참조 방식

```js
/* 생성자 함수로 인스턴스를 생성하는 경우 */
function ConstructorFunctionCircle(radius) {
    // 이 시점에는 생성자 함수가 자신을 생성할 인스턴스를 가리키는 식별자를 알 수 ❌
    ???.radius = radius;

    ConstructorFunctionCircle.prototype.getDimeter = function () {
        // 이 시점에는 생성자 함수가 자신을 생성할 인스턴스를 가리키는 식별자를 알 수 ❌
        return 2 * ????.radius
    }
}

/* 생성자 함수로 인스턴스 생성 시 먼저 생성자 함수를 정의해야 한다*/
const circle = ConstructorFunctionCircle(5)
```

**생성자 함수 내부에 프로퍼티 및 메서드 추가시 자신이 생성할 인스턴스를 참조할 수 있어야한다**

- 생성자 함수를 정의하는 시점에는 아직 해당 인스턴스가 생성되기 이전이므로 생성자 함수가 생성할 인스턴스를 가리키는 식별자를 알 수 없음
  - 이를 위해 자바스크립트 엔진은 `this`라는 특수한 식별자 키워드를 제공한다.

### this 정의

**this란?**

- 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수
- `this`는 엔진에 의해 암묵적으로 생성
  - 따라서 코드 어디서든 참조할 수 있다
- **this**가 가리키는 값은 함수 호출 방식에 따라 동적으로 결정된다

### `this`가 가리키는 값은 함수 호출 방식에 따라 동적으로 결정된다

**전역에서의 this**

- `window`를 참조한다

```js
/* this가 가리키는 값은 상황에 따라서 다르다 */

/* 전역에서의 this*/
console.log(this); // window
```

**일반함수에서의 this**

- `window`를 참조한다

```js
/* 일반함수에서의 this */
function normalFunction() {
  console.log(this); // window
}
normalFunction();
```

**객체 내부 메서드 단축표현**

- 메서드를 호출한 객체를 가르킨다

```js
/* 객체 내부 메서드 단축표현 */
const person = {
  name: "Seju",
  getName() {
    console.log(this);
  },
};

person.getName(); // {name: 'Seju', getName: ƒ}
```

**생성자 함수에서의 this**

- 생성자 함수가 생성할 인스턴스를 가르킨다

```js
/* 생성자 함수에서의 this */
person.getName();
function ConstructorFunction() {
  console.log(this); // ConstructorFunction {}
}

const cFunc = new ConstructorFunction();
```

**this는 객체의 메서드/ 생성자 함수 내부에서만 의미 있음**

- 따라서 strict mode에선 일반 함수 및 전역 변수에서의 `this`는 `undefined`가 나온다

> **❓ 콜백함수가 일반함수로 호출될때의 this?**

**콜백 함수 내부의 `this`도 전역객체인 `window`로 바인딩**

```js
/* 콜백함수가 일반함수로 호출될때의 this */
var value = 1;
const valueObject = {
  value: 100,
  foo() {
    console.log(`Foo this : ${this.value}`); // 100
    // 콜백함수 내부 this는 전역객체가 바인딩된다
    setTimeout(function () {
      console.log(`콜백함수의 ${this.value}`); // undefined
    }, 1000);
  },
};
valueObject.foo();
```

**이처럼 일반 함수로 호출된 모든 함수 내부의 this는 전역객체에 바인딩된다**

- 그러나 콜백함수가 일반 함수로 호출될 때 `this`가 전역객체를 바인딩하는것은 문제가 있다.

**콜백함수에서의 this바인딩을 일치시키는 방법**

- 함수 내부의 임의의 변수를 `this`에 할당하고
  - 콜백함수에 지정한 해당 변수를 `this`처럼 사용
  - 위 방법 외에도 `this`를 명시적으로 바인딩할 수 있는 `apply/call/bind` 메서드 사용 가능

```js
/* 콜백함수에서의 this를 "제대로" 바인딩하기 */
const valueObject2 = {
  value: 100,
  foo() {
    const that = this;
    console.log(`Foo this : ${this.value}`);
    // 콜백함수 내부 this는 전역객체가 바인딩된다
    setTimeout(function () {
      console.log(`콜백함수의 ${that.value}`); // 콜백함수의 100
    }, 1000);
  },
};
valueObject2.foo();
```

<br />

## 호출 방식에 따른 this 바인딩 정리

| 함수 호출 방식                  | this 바인딩                                 |
| ------------------------------- | ------------------------------------------- |
| 일반 함수 호출                  | 전역객체 (window)                           |
| 생성자 함수 호출                | 생성자 함수가 미래에 생성할 인스턴스        |
| apply/call/bind에 의한 간접호출 | apply/call/bind에 첫번째 인수로 전달한 객체 |
