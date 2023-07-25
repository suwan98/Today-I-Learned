# toSorted() /toReversed() /toSpliced()

---

>  🚨 해당 세개의 메서드는 현재 표준화 되지않았지만 기술이 추가될 가능성이 높다.

- 기존 `Array.sorted` / `Array.sort` / `Array.splice`는 기존 원본 배열이 훼손되는 문제점이 존재했다
- 해당 메서드는 기존의 문제점을 보완한 메서드이며, 기능은 기존과 동일하게 동작하지만, **원본배열을 훼손하지않고 새로운 배열을 반환받을 수 있게된다**

## Array.toSorted()

- `Array.toSorted`는 비교함수에 의해 배열을 정렬할 수 있다
- 기존 `sort()`와 달리 원본배열에 영향 ❌

```js
const arr1 = [1,3,4,5,67,123,512]
const sortedArr = arr1.toSorted((a,b) => a-b) // 새 변수를 정해 그 변수에 toSorted한 값을 저장

console.log(arr1) // [1,3,4,5,67,123,512]
console.log(sortedArr) // [[1, 3, 4, 5, 67, 123, 512]]

```

<br />

## Array.toReversed()

- `Array.toReversed`는 배열을 거꾸로 뒤집을 수 있다.
- 기존 `reverse`와 달리 원본 배열해 영향 ❌

```js
const arr = [1,2,3]
const reversedArr = arr.toReversed();  // 새 변수를 정해 그 변수에 toReversed한 값을 저장

console.log(arr) // [1,2,3]
console.log(reversedArr) // [3,2,1]
```

<br />

## Array.toSpliced()

- `Array.toSpliced`는 배열에서 특정요소를 삭제하거나, 교체 및 새요소를 추가할 수 있따
- 기존 `splice`와 달리 원본 배열에 영향 ❌

```js
const arr = [1, 2, 3, 4, 5];
const newArr = arr.toSpliced(1, 0, 'new1');

console.log(arr);         // [1, 2, 3, 4, 5];
console.log(newArr);      // [1, "new1", 2, 3, 4, 5]
```