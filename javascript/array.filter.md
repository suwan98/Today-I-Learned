# 배열의 Array.fillter() 메서드

- `Array.prototype.filter()` 메서드는 주어진 조건을 충족하는 요소로만 구성된 **새로운 배열로 반환**한다
- 조건은 콜백함수를 사용하여 정의
- 해당 함수는 배열의 각 요소에 접근해 적용 됨
- 콜백함수가 true를 반환하면 해당 요소가 배열에 포함된다

## Array.fillter() 예시 (1)
```jsx
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
// number라는 임의의 변수를 받아 number에서 2로 나눴을때 0이 되는값, 즉 짝수만을 추출
const evenNumbers = arr.filter(number => number % 2 === 0);
console.log(evenNumbers);  // [2,4,6,8]
```

## Array.fillter() 예시 (2) 
- 아래 코드처럼 한줄 이상의 값이 콜백함수에 들어갈땐
- `return` 키워드로 명시적으로 결과를 반환해줘야한다
  
```jsx
const numbers = [2, 5, 1, 7, 4, 10, 3];

const greaterOrEqual5 = numbers.filter((number) => {
    const condition = number >= 5;
    return condition;
})

console.log(greaterOrEqual5) // [5,7,10]
```

## Array.fillter() 예시 (3) 
- `fillter()` 메서드는 숫자뿐만이아니라 문자열의 추출에서도 사용가능하다

> 특정 글자로 시작하는 문자열만 추출하기

```javascript
const fruits = ['apple', 'banana', 'avocado', 'grape'];

// fruits의 item들의 첫번째글자(fruit[0])를 소문자로 반환(.toLowerCase)의 값이 'a'와 같은 것들만 추출
const aFruits = fruits.filter(fruit => fruit[0].toLowerCase() === 'a');
console.log(aFruits); // ['apple', 'avocado']
```