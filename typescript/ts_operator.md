# 타입스크립트에서 타입연산자

## 타입 연산자(Type Operators)

- 자주사용되는 타입연산자들 3가지에 대해서 정리해보았다.

### 1. typeof 연산자

**타입스크립트에서의 `typeof`**

- `JavaScript`에선 값을 통해 타입을 체크하는 연산자
- 타입스크립트에선 `typeof`연산자를 통해 타입을 가져올 수 있다
  - 변수가 있고 해당 변수의 타입을 가져오면 `typeof` 연산자를 통해 해당 변수를 타입처럼 사용할 수 있게된다

```ts
let s = "hello";
let n: typeof s; // 'n'의 타입은 's'와 동일한 'string'이 됩니다.
```

### 2. keyof 연산자

**keyof 연산자**

- 객체 타입의 모든 키를 문자열 리터럴 타입의 유니온으로 반환
- 이를 통해 객체의 키에 접근하거나 객체의 키를 제한하는데 사용할 수 있게된다

```ts
type Point = {x: number; y: number};

/* keyof으로 Point 객체 타입의 키만 빼오기*/
type P = keyof Point; // 이제 P 타입은 'x' | 'y' 유니온타입이된다
```

### 3. in 연산자

**in 연산자**

- 객체의 키가 있는지 확인하는데 사용할 수 있다
- 타입스크립트에선 해당 타입의 키를 검사하는데 사용할 수 있다
  - 타입가드 생성
  - 아래 코드에서 `toFixed`는 number 타입에만 존재하는 메서드이므로 `value`가 `number`타입인지 확인하는 타입가드의 역할을 하게 된다

```ts
function doSomething(value: number | string) {
  if ("toFixed" in value) {
    console.log(value.toFixed(2)); // 이 블록에서 'value'는 'number' 타입이라고 보장됩니다.
  } else {
    console.log(value.toUpperCase()); // 이 블록에서 'value'는 'string' 타입이라고 보장됩니다.
  }
}
```
