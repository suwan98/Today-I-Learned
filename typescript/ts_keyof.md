# 타입스크립트에서의 keyof 연산자

## keyof?

**타입스크립트의 keyof 연산자**

- 객체 타입에서 객체의 키 값들을 숫자나 문자열 리터럴 유니언을 생성
- 아래 코드에서타입 P는 `"x" | "y"` 와 동일

```tsx
type Point = {x: number; y: number};

// `"x" | "y"` 와 동일
type Pkeys = keyof Point;
```

**만약 타입이 `string`이나 `number` 인덱스 시그니쳐를 가지고 있다면?**

- `keyof` 연산자는 해당 타입을 반환한다
- 두번째 M 타입의 타입은 왜 `stirng | number`로 타입추론될까?
  - `JavaScript` 객체 키는 항상 문자열을 강제하므로 `obj[0]` 은 `obj["0"]`과 동일하다

```ts
type Arrayish = {[n: number]: unknown};
// A의 타입은 Arraylist 타입의 인덱스시그니쳐 타입인 number이다
// type A = number
type A = keyof Arrayish;

type Mapish = {[k: string]: boolean};
// M의 타입은 Mapish 타입의 인덱스시그니쳐 타입인 string | number이다
type M = keyof Mapish;
```
