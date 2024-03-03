# 타입스크립트에서 interface와 type의 차이점

## 타입의 확장 시 문법 차이

### interface

- interface는 extends 키워드를 통해 확장할 수 있다.

```ts
interface Person {
  name: string;
  address: string;
}
```

### type

- type은 & 키워드를 통해 확장할 수 있다.

```ts
type Person = {
  name: string;
  age: number;
};
```

## 선언적 확장의 유무

### interface

- interface는 같은이름의 interface를 선언하면, 그 interface는 자동적으로 확장된다(=선언적 확장)
- 그러나 type은 선언적 확장이 불가하다.

```ts
interface Person {
  name: string;
  address: string;
}

/* 선언적 확장 */
interface Person {
  age: number;
}
```

## 원시자료 타입 선언 시

### interface

- inteface는 오직 **객체**타입을 설정할 때 사용할 수 있으며, 원시자료형은 사용불가하다.
- 따라서 원시값,튜플,유니온타입등을 사용할땐 `type`을 사용하는것이 더 좋다.

```tsx
interface Person {
  name: string;
  age: number;
  gender: string;
}

/* 불가능 */
interface name etendes string {}

```
