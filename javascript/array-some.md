# Array.prototype.some 메서드

## 기능

`some`메서드는 비교할 배열과 주어진 콜백함수 조건에서 하나라도 일치하면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.

- 첫번째 인자로 콜백함수가 들어갑니다.
  - 콜백함수의 매개변수로는 첫번째는 처리할 배열의 현재 요소, 두번째는 처리할 현재 요소의 인덱스, 세번째는 `some` 함수를 호출한 배열 그자체가 들어갑니다.
- 두번째 인자는 옵션이며, `thisArg`, 콜백함수를 실행할때 `this`로 사용하는 값이 들어갑니다.

```js
const arr = [1, 2, 3, 4, 5];

/* arr 배열을 순회해 item 중 하나라도 2보다 하나라도 작은 값이 있으므로 true를 반환한다 */
arr.some((item) => item < 2); // true
```