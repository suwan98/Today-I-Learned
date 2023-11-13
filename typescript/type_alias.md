# 타입 별칭 (Type Alias)

## 타입 별칭의 정의

- 타입 별칭이란 특정 타입이나 인터페이스를 참조할 수 있는 타입 변수를 의미

```ts
// string 타입을 사용할 때
const name: string = "capt";

// 타입 별칭을 사용할 때
type MyName = string;
const name: MyName = "capt";

type Developer = {
  name: string;
  skill: string;
};
```

**타입 별칭에도 제네릭을 부여할 수 있다**

```ts
type User<T> = {
  name: T;
};
```

## 타입 별칭의 특징

- 타입별칭은 새로운 타입 값을 하나 생성하는것이 아닌 정의한 타입에 대해 참고할 수 있도록 이름을 부여하는 것
- 따라서 인터페이스와 달리 `VSCode`에서 프리뷰 상태로 타입을 확인할 수 있다
