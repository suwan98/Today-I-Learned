# 변수의 생명주기

## 지역변수의 생명주기

**변수는 선언에 의해 생성되고 할당을 통해 값을 가진다. 그리고 언젠가 소멸한다**

- 즉 변수는 **생명주기**가 존재한다
  - 변수는 자신이 선언된 위치에서 생성하고 소멸한다
  - 전역변수의 생명 주기는 애플리케이션의 생명주기와 같다
  - 그러나 함수 내부에 선언된 지역변수는 다르다
    - 함수가 호출되면 **생성**되고 ➡️ 함수가 종료되면 **소멸**한다

**코드로 살펴보기**

- 아래 코드에서 지역 변수 `x`는 `foo()`함수의 호출전까지는 생성되지 ❌
- `foo()` 함수가 호출되면 `x` 변수가 생성된다
- `x`변수는 `console.log(x)`에서 사용되고 함수가 종료되기 전까지 유지된다
- 함수가 종료되면, `x` 변수는 소멸한다
  - 따라서 최종적으로 `console.log(x)` 이후에 `x`변수를 참조하려고하면 `x is not defined`라는 오류가 발생할 것이다

```js
function foo() {
  var x = "지역변수"; // 지역변수
  console.log(x); // 지역변수
  return x;
}

foo();
conosole.log(x); // x is not defined
```