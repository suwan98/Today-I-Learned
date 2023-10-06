# Typescript Interface

## 인터페이스 정의

- 객체의 구조를 정의
- 객체가 어떻게 구성되어야 할지
- 타입스크립트만 지원
- 대문자로 시작해야하는 컨벤션을 가진다
- 구조는 정의할 수 있지만 값의 할당은 불가하다

```tsx
interface Person {
  name: string;
  age: number;
  isValid: boolean;
}
```

### 프로퍼티를 정해서 객체를 표현하고자 할때는? ➡️ 인터페이스

```tsx
interface User {
  name: string;
  age: number;
}

let user: User = {
  name: "seju",
  age: 26,
};
```

**없는 프로퍼티를 수정하려고하면? 마찬가지로 에러**

```tsx
user.age = 10;
// Error
user.gender = "male";
```

### 인터페이스 함수 정의

**인터페이스는 함수의 구조를 정의하는데에도 사용할 수 있다**

- 함수도 객체의 일부이므로 인터페이스로 대체할 수 있다
- 메서드이름은 작성 ❌

**Add 함수형인터페이스**

- 매개변수로 `num1,num2` 2개인 `number`타입을 받으며 반환값도 `number`타입이어야 함

```tsx
interface Add {
  (num1: number, num2: number): number;
}
```
