# TypeScript 내에서 유효한 타입들

## 튜플(Tuple) 타입

- 고정된 요소 수와 타입을 가진 배열을 표현할 수 있는 타입이다

```jsx
let person: [string, number];
person = ["John", 30];
```

## 열거(Enum) 타입

- - 값의 집합에 더 나은 이름을 붙여줄 수 있다
- `enum`은 `0`부터 시작하여 멤버들의 번호를 매긴다
  - 멤버 중 하나의 값을 수동으로 설정해, 번호를 바꿀 수도 있다

```jsx
enum Color {
  Red,
  Green,
  Blue,
}

let selectedColor: Color = Color.Red;

```

## 유니온 타입

- 여러 타입 중 하나가 될 수 있는 타입이다 (||)

```jsx
let result: number | string;
result = 42;
result = "Hello";
```

## 리터럴 타입

- 값 자체가 타입으로 사용되는 타입

```jsx
let status: "success" | "error";
status = "success";
```

## 함수 타입

- 함수의 매개변수 및 반환 타입을 정의하는 타입

```jsx
type MathFunction = (x: number, y: number) => number;

const add: MathFunction = (x, y) => x + y;
```

## void

- 반환 값이 없는 함수나 변수에 사용되는 타입

```jsx
function logMessage(message: string): void {
  console.log(message);
}
```

## never

- 함수가 항상 예외를 던지거나, 무한 루프에 빠지는 경우를 나타내는 타입

```jsx
function throwError(message: string): never {
  throw new Error(message);
}

function infiniteLoop(): never {
  while (true) {}
}
```
