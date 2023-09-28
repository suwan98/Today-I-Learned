# Javascript Type 선언

### 문자열타입의 선언

```jsx
let str: string;
let red: string = "Red";
let green: string = "Green";
let myColor: string = `My Color is ${red}`;
let yourColor: string = "Your Color is" + green;
```

### 숫자타입의 선언

```jsx
let num: number;
let integer: number = 6;
let float: number = 3.14;
let infinity: number = Infinity;
let nan: number = NaN;
```

### Null/Undefinded 타입의 선언

**거의 지정할 일 ❌**

```jsx
let null : null
let und : undefined

```

### 배열 타입의 선언

**배열의 타입선언은 그안에 들어갈 아이템타입과 배열을의미하는 대괄호를 항상 같이사용해줘야 한다**

```jsx
const fruits: string[] = ["Apple", "Banana", "Cherry"];
const numbers: number[] = [1, 2, 3, 4, 5, 6, 7];
const union: (string | number)[] = ["Apple", 1, 2, "Bananan"];
```

### 객체 타입의 선언

**객체타입의 사용**

- 자바스크립트는 객체 내부에 배열,함수가 포함되어있는 형태이기때문에 배열,함수도 전부 허용되므로 거의 이렇게 사용 ❌

```jsx
const obj: object = {};
const arr: object = [];
const func: object = function () {};
```

**객체타입의 올바른 선언**

- 할당 되는 데이터와 변수 사이에 속성과 타입을 지정한다

```jsx
const user1 : {
	name : string,
	age : number,
	isValid : boolean
} = {
	name : 'Seju'
	age : 26
	isValid : true

}
```

**객체타입의 interface를 사용해 재활용**

- 인터페이스로 만들어진 하나의 타입을 만들면 재활용 가능
- 그러나 인터페이스가 지정해졌기때문에 다른 속성을 추가 ❌

```jsx
**interface User {
	name : string,
	age : number,
	isValid : true
}**

const user1 : User = {
	name : 'Seju'
	age : 26
	isValid : true
}

const user2 : User = {
	name : 'James'
	age : 28
	isValid : false
/* 인터페이스가 오버라이드 되었기때문에 새로 지정 불가 */
	~~**email : ''**~~
}
```

### 함수 타입의 선언

<aside>
🌅 **함수 타입 설명**

</aside>

**add 함수 타입 설명**

- 매개변수로 오직 `number`만 받고 반환값도 `number`이다

**hello 함수 타입 설명**

- 매개변수로 아무것도 받지 않는다(`void`)

```jsx

/* 반환값이 존재하는 함수의 선언 */
const add : **(x:number, y:number) => number** = function(x,y){

	return x + y
}

const **a:number** = add(1,2)

/* 반환값이 존재하지 않는 함수의 타입선언 */
const hello**: () => void** = function () {
	console.log('Hello')
}

const h:void = hello()
```
