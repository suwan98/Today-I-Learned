# instanceof 연산자

## instanceof 란?

**`instanceof` 연산자 사용 시 해당 객체가 특정 클래스에 속하는지 아닌지를 확인할 수 있다**

- `instaceof`는 상속관계도 확인할 수 있음

## instanceof 연산자 문법

**obj가 `Class`에 속하는 인스턴스이거나 `Class`를 상속받는 클래스에 속하면 `true`가 반환**

```js
obj instaceof Class
```

### instaceof 예시

**rabbit 인스턴스가 Rabbit Class의 인스턴스인지 아닌지 확인**

```js
class Rabbit {}
let rabbit = new Rabbit();

// rabbit이 클래스 Rabbit의 객체인가요?
alert(rabbit instanceof Rabbit); // true
```

**instanceof는 생성자 함수에서도 사용할 수 있다**

```js
// 클래스가 아닌 생성자 함수
function Rabbit() {}

alert(new Rabbit() instanceof Rabbit); // true
```

**Array 같은 내장 클래스에도 사용할 수 있다**

```js
let arr = [1, 2, 3];
alert(arr instanceof Array); // true
alert(arr instanceof Object); // true
```
