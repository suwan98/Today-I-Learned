<h1>배열</h1>
<br>
<h2>Array(배열)</h2>
자바스크립트에 있는 자료구조 중 하나 <br/>
프로그래밍에서 index는 0부터 시작한다

<br/>

<hr/>

**배열의 선언**
```javascript
//1. 배열의 선언
const arr = new Array()
const arr2 = [1, 2]
```

**Index postition**
```javascript
//2.  Index postion
const fruits = ["apple", "banana"];
console.log(fruits);
console.log(fruits[0]); //apple
```

<br/>
<hr/>

<h2>Lopping over an array</h2>

<br/>

>1. for문을 활용한 접근
```javascript
// a. for
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

<br/>

>2. for of문을 활용한 접근

let이라는 변수에 데이터를 한번씩 순차적으로 할당하면 블록을 실행

```javascript
// b. for of
for (let fruit of fruits) {
  console.log(fruit);
}
```

<br/>

>3. for each문을 활용한 접근

`forEach()` 함수는 첫번째 parameter로 콜백함수를 받는다
1. 첫번째 parameter (콜백 함수)
2. 두번째 parmeter (index)
3. 세번째 array(전체)

<br />

```javascript
// c. for each
fruits.forEach((fruit, index, array) => {
  console.log(fruit, index, array);
});
```

<br />

>4. Add / delete / copy

```javascript
// push : add item to the end
fruits.push("grape");
console.log(fruits); //['apple', 'banana', 'grape']

// pop : delete item to the end
fruits.pop();
console.log(fruits); //['apple', 'banana']
```

<br />

>5. 앞에서 추가 / 삭제는?

**unshift()** : 앞에서 **추가**

**shift()** : 앞에 값 **제거**

```javascript

fruits.push("grape");
console.log(fruits);
fruits.unshift("strewbray");
console.log(fruits);
```

<br />

>6 .아이템을 지정된 포지션에 지우는 건?

`array.splice()`

```javascript

// splice : remove an item by index position
fruits.push("복숭아", "레몬", "메론");
console.log(fruits);
fruits.splice(3, 3); //index 3에서부터 ~ 3개를 지워줘
console.log(fruits);
```
<br />

만약 두번째 인수(~~까지 지워줘)를 지정하지 않는다면?

아래 코드 처럼 **1부터 시작해서 전부 지워버린다(0인 ‘strewbary’만 존재하는 모습)**

```javascript
// splice : remove an item by index position
fruits.push("복숭아", "레몬", "메론");
console.log(fruits);
fruits.splice(1);
console.log(fruits); //['strewbray'] 
```

splice() 세번째 옵션은 추가 기능 이 있음
```javascript
// splice : remove an item by index position
fruits.push("복숭아", "레몬", "메론");
console.log(fruits);
fruits.splice(1, 1, "레거시 코드"); //1부터 1까지 지우고 그 자리에 레거시 코드 삽입
console.log(fruits); //['strewbray', '레거시 코드', 'banana', '복숭아', '레몬', '메론']
```

<br />

> 7.Array.concat()

원본의 배열 변경없이 배열이나 값들을 기존 배열에 합쳐 **새 배열을 반환**
- 기존 배열을 변경하지 않는다
- 추가된 새로운 배열을 `리턴`한다
  
  
```javascript
// 두개의 어레이를 합체
const fruits2 = ["망고", "코코넛"];
const newFruits = fruits.concat(fruits2);
console.log(newFruits);
  ```

<br />

> 8. 배열의 검색


 **`indexOf`**

해당 배열의 **인덱스 값**을 리턴
```javascript
console.log(fruits); //['strewbray', '레거시 코드', 'banana', '복숭아', '레몬', '메론']
console.log(fruits.indexOf("레거시 코드")); //1
  ```

  **`inclueds`**

  해당 배열이 존재 하는지 **불리언 값**으로 리턴
  ```javascript
console.log(fruits);
console.log(fruits.includes("망고")); //false
console.log(fruits.includes("레거시 코드")); // true

  ```