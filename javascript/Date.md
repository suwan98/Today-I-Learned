<h1>Date() 함수 자세히 알아보기 🚀</h1>

## 1. Date()

- `Date()`는 자바스크립트의 표준 내장객체이다
- Javascript의 날짜의 기반은 1970년 1월 1일 UTC 자정과 시간 차이를 밀리초 단위로 나타낸 것이다
  
    <img src="https://i.imgur.com/9IOh8iX.png" />
  
    <img src="https://i.imgur.com/xLXcy0K.png" />


### 1.1 생성자

- `Date()`
  - 함수로 호출시, `new Date().toString()`과 동일하게
  - **현재 날짜와 시간**을 나타내는 문자열을 **반환**

```javascript
const date = Date();
console.log(date) // "Fri Jun 30 2023 00:24:39 GMT+0900 (한국 표준시)" ➡️ String으로 반환된 모습
``` 

- `new Date()`
 - 생성자로 호출 시 **새로운 Date 객체**를 **반환**

<br/>
<hr />
<br />

## 2. 정적 메서드

- `Date.now()`
  - 1970년 1월 1일 00:00:00 UTC로 부터 지난 시간을 밀리초 단위의 숫자값으로 반환
  
  ```javascript
    const now = Date.now();
    console.log(now) //1688052465160
  ```

<br/>
<hr />
<br />

## 3. 인스터스 메서드

- `Date.getDate()`
  - Date에서 **현지 시간 기준 일(1~31)**을 반환

```javascript
    const now = new Date();
    console.log(now.getDate()) //현재 날짜가 30일 이므로 30 출력
```

<br/>


- `Date.getDay()`
  - Date에서 **현재 시간 기준 요일( 0~6 ➡️ 일요일부터(0) ~ 토요일까지(6) ) 반환
  - 🚨 1~7까지가 아닌 0~6까지이다!
  
  ```javascript
    const now = new Date();
    console.log(now.getDay()) // 현재 6월 30일이 금요일이므로 5를 반환
  ```

<br/>


- `Date.getFullYear()`
  - Date에서 현지 시간 기준 연도(네자리 연도면 네자리로)를 반환

 ```javascript
    const now = new Date();
    console.log(now.getFullYear()) // 현재 2023년이므로 2023 반환
  ```

<br/>


- `Date.getMilliseconds()`
  - Date에서 현지 시간 기준의 밀리초(0밀리초에서 999밀리초까지)를 반환

<br/>


- `Date.getMinutes()`
  - Date에서 현지 시간 기준의 분(0분에서 59분까지)을 반환

<br/>

  
- `Date.getMonth()`
  - Date에서 현지 시간 기준 월(0~11 ➡️ 1월(0) ~ 12월까지 (11)) 반환

```javascript
const now = new Date();
console.log(now.getMonth()) // 현재 6월이므로 5를 반환
```

<br/>


- `Date.getTime()`
  - 1970년 1월 1일 00:00:00 부터의 경과 시간을 밀리초 단위로 반환

```javascript
const now = new Date();
console.log(now.getTime()) // 1688053160379 -> 1970년도 부터 지금까지의 경과시간을 밀리초단위로 반환
```
<br/>
<hr />
<br />

## 4. javscript에서 Date() 객체 활용 예시

- 1. 현재시간 구하기
  `const now = new Date();`  ➡️ now 변수에 현재시간을 담을 수 있다

<br/>


- 2. 특정 날짜 및 시간으로 Date 객체 생성
  `const X-mas = new Date(2023,12,25,00,00,0)` ➡️ 2023년 12월 25일 자정 00시 00분 0초

<br/>


- 3. 현재 `Date` 객체에서의 연,월,일,시간,분,초 값 구하기
  
  ```javascript
    const year = now.getFullYear(); // 연도(4자리)
    const month = now.getMonth() + 1; // 월(0부터 시작하므로 1을 더함)
    const day = now.getDate(); // 일
    const hour = now.getHours(); // 시
    const minute = now.getMinutes(); // 분
    const second = now.getSeconds(); // 초
  ```


<br/>

- 4. 특정 포맷으로 날짜 및 시간 출력
  
  ```javascript
    const formatted = now.getFullYear() + '-' + (now.getMonth() + 1) + '-' + now.getDate() + ' ' + now.getHours() + ':' + now.getMinutes() + ':' + now.getSeconds(); // 예: "2022-1-1 14:30:0"

  ```

<br/>


- 5. 특정 날짜와 시간의 차이 구하기

    ```javascript
    const start = new Date(2022, 0, 1); // 2022년 1월 1일
    const end = new Date(2022, 0, 15); // 2022년 1월 15일
    const diff = end.getTime() - start.getTime(); // 밀리초 단위로 차이 계산
    const days = Math.floor(diff / (1000 * 60 * 60 * 24)); // 일 단위로 계산

    ```