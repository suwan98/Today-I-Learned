# 자바스크립트에서의 콜백함수(Callback function)

## 정의 및 용도

- 콜백함수는 어떤 함수의 파라미터로 들어가는 함수이다.
- 함수를 인수로 전달하여, 다른 함수에 해당 함수를 파라미터로 받는 함수이다.
- 용도는 순차적으로 실행하고 싶을때 사용한다.
  - 대표적으로 `async/await` 및 `setTimeout`,`addEventListener`, `forEach()` 등등..
- 자바스크립트에서 함수는 객체이다, 따라서 함수의 파라미터로서 객체를 전달할 수 있다.
- 즉, **콜백 함수란 파라미터로 일반적인 변수나 값을 전달하는 것이 아닌 함수 자체를 전달한다**
- 보통 콜백 함수 형태로 함수를 넘겨줄때는 익명함수 형태로 넣어주게된다



## 콜백함수 예제

```js
function sayHello(callback) {
  var name = "Alice";
  callback(name); // 콜백 함수 호출
}

// 익명 화살표 콜백 함수
sayHello((name) => {
  console.log("Hello, " + name);
}); // Hello, Alice

```

- 위코드에서 sayHello라는 함수를 인수로 `sayHello`의 매개변수인 `callback`으로 전달하고 있다

```js
function print(callback) {
    callback();
}
```

- 위 코드에서`print()` 함수는 매개변수로 callback이라는 변수를 받아 내부에서 그것을 호출하고 있다.


```js
const btn = document.querySelecor('.button')

btn.addEventListener('click', function(){

})

```

- 여기서 `addEventListener()`함수 안에들어가는 `익명함수 function` 즉 ➡️ 이게 **콜백함수**이다

