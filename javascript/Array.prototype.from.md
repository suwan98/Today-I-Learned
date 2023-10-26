# Array.from()

## Array.from() 정의

**`Array.from()` 메서드는 이터러블 객체나 유사배열 객체에 대한 얕게 복사된 새로운 Array 인스턴스를 생성**

## Array.from() 구문

```js
Array.from(arrayLike);
Array.from(arrayLike, mapFn);
Array.from(arrayLike, mapFn, thisArg);
```

### 매개변수

**arrayLike** (필수)

- 배열로 변환할 이터러블 객체 또는 유사배열 객체

**mapFn** (옵션)

- 배열의 모든 요소에 대해 호출할 함수
- 해당 함수 제공 시 배열에 추가할 모든 값이 이 함수를 통해 먼저 전달
- `mapFn`의 반환 값이 대신 배열에 추가
- 이 함수는 다음 인수를 사용해 호출
  - `element`
    - 배열에서 처리 중인 현재 요소
  - `index`
    - 배열에서 처리 중인 현재 요소의 인덱스

**thisArg** (옵션)

- `mapFn` 실행 시 `this`로 사용할 값

### 반환값

**새로운 Array 인스턴스를 반환**

## Array.from() 예시

**`NodeList`는 대표적인 유사배열 객체이다 해당 유사배열객체를 `Array.from()`메서드로 일반배열로 변환**

```js
const elements = document.querySelectorAll(".example-class");

/* 현재 유사배열 객체인 elements를 Array.from 메서드로 일반배열로 변환*/
const elementArray = Array.from(elements);
```
