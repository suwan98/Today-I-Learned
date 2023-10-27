# 타입 서술어

## 타입 서술어(Type Predicates)란?

- 타입가드의 일종
- 타입 서술어는 타입스크립트에서 변수의 타입을 좁히는데 사용되는 함수 또는 코드 패턴
- 타입 서술어 함수는 `boolean` 값을 반환하고 반환타입에 `value is type`을 지정해주는 함수를 뜻한다.
- 반환값이 `true`일 경우, 해당 블록에서는 값이 해당 타입이라는것을 타입스크립트가 알 수 있게 된다.

## 타입 서술어 예시

- `isRequiredAndNumberAndNotZero` 함수에서 매개변수 `value`는 어떤 값이든 받을 수 있다
  - `value is number` 부분은 함수에서 `true`를 반환할때 `value` 반환값이 `number`로 좁혀짐을 의미한다
  - 함수가 `true`를 반환 시 타입스크립트 컴파일러는 해당 변수가 숫자임을 알고 이에 따라 숫자와 관련된 작업을 수행할 수 있게 한다.

```ts
const isRequiredAndNumberAndNotZero = (value: any): value is number => {
  return isNumber(value) && isNotZero(value) && isRequired(value);
};
const isRequired = (value: any): value is any => {
  return value !== null && value !== undefined;
};

const isNumber = (value: any): value is number => {
  return typeof value === "number";
};

const isNotZero = (value: number | string): value is number => {
  return Number(value) !== 0;
};
type StringOrNumber = string | number;

const data: StringOrNumber = await fetchData();

if (isRequiredAndNumberAndNotZero(data)) {
  console.log(data + 10);
} else {
  console.log(data + "십");
}
```

### value:number 와 value is number의 차이점은?

**타입가드의 유무**

- `:number` : 이렇게 정의하면 타입스크립트에게 함수의 입력값이 어떤 타입이어야하는지 정의하는 것
- `: value is number` : 타입스크립트에서 타입가드 역할
  - 반환타입에 `value is number`를 명시함으로 해당 함수가 `true`를 반환 시 `value` 타입이 `number`로 좁혀짐을 의미
- 즉, `value is number`는 함수의 반환값이 `true`일 때 변수의 타입을 좁히는 역할을 하는 반면, `value:number`는 매개변수 타입을 정적으로 선언하는 역할을 한다
