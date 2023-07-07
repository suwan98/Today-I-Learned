# String.prototype.trim()

<br />

## 🧑‍🚀 trim() 메서드란?

<hr />

- 문자열 **양 쪽 끝의 공백을 제거** 후, 원본 문자열을 수정하지 않고 **새로운 문자열**을 **리턴**

<Br />

## 🧑‍🚀 trim() 메서드 예제

<hr />

```js

const str = '       Hello!'
const newString = str.trim();

console.log(str) // '         Hello'
console.log(newString)// 'Hello' //위의 원본 문자열이 유지 되면서 공백만 제거함


```