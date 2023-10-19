# Array.prototype.every() 메서드

## Array.every란?

- 배열의 모든 요소가 제공된 함수로 구현된 테스트를 통과하는지 테스트
- 해당 메서드의 반환값은 `boolean`

## 구문

```js
every(callbackFunction);
every(callbackFunction, thisArg);
```

### 매개변수

**`callbackFunction`**

- 배열의 각요소에 대해 실행할 함수
  - 요소가 테스트를 통과하면 `true`를 반환 아니면 `false`를 반환
  - 해당 콜백함수는 아래와 같이 3개의 인자를 받을 수 있다
    - `element` (필수)
      - 배열에서 처리되는 현재 요소
    - `index` (옵션)
      - 처리되는 현재 요소의 인덱스
    - `array` (옵션)
      - `every()` 메서드를 호출한 배열

**`thisArg` (Option)**

- 콜백함수를 실행 할 때 `this`로 사용하는 값

### 반환값

- 콜백함수가 모든 배열 요소에 대한 `truthy`한 값을 반환하면 `true``
- 그러하지 않으면 `false`

## 예제 코드

**배열의 모든 요소가 9보다 더 큰지 테스트**

```js
function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough); // false
[12, 54, 18, 130, 44].every(isBigEnough); // true
```

**한 배열이 다른 배열의 부분 집합인지 확인**

- 배열의 모든 요소가 다른 배열에 존재하는지 테스트

```js
const isSubset = (array1, array2) =>
  array2.every((element) => array1.includes(element));

console.log(isSubset([1, 2, 3, 4, 5, 6, 7], [5, 7, 6])); // true
console.log(isSubset([1, 2, 3, 4, 5, 6, 7], [5, 8, 7])); // false
```

> 📝 **유사배열 객체에서의 사용**

- ArrayLike 객체는 배열이 아니므로 `Array.prototype.every.call`을 사용해 빌려써야함

```js
const arrayLike = {
  length: 3,
  0: "a",
  1: "b",
  2: "c",
  3: 345, // length가 3이므로 every()에 의해 무시됩니다.
};
console.log(
  Array.prototype.every.call(arrayLike, (x) => typeof x === "string")
); // true
```
