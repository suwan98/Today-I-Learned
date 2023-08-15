# OR 연산자와 AND 연산자

---

## OR 연산자 (||)

- 첫번째 truthy한 값을 찾는 연산자
- 하나 이상이 `true` 일 경우 전체 표현식을 `true`로 평가하는 역할
- or 연산자를 사용시 조건식1이 `true`라면, 전체 표현식은 `true`로 평가
- 조건식1이 false 인 경우 조건식 2가 평가되고 조건식 2까지 `false`라면 전체 표현식은 `false`로 평가

```js
조건식1 || 조건식2;

alert(true || true); // true
alert(false || true); // true
alert(true || false); // true
alert(false || false); // false
```

### OR 연산자의 피연산자가 여러개일 경우?

- 아래 코드에서 value1이 `0`이고, value2가 `1`이고 value3이 `''`일 경우, 첫번째로 만나는 true 값인 value2의 값이 반환된다

```js
result = value1 || value2 || value3;
```

> ❓ 만약 여기서 평가되는 값이 전부 `false`라면

- value1,value2,value3이 전부 `false`로 평가되는 값이라면, 해당 식의 가장 마지막 값(=여기선 value3)의 값이 반환된다.

---

## AND 연산자 (&&)

- 각 피연산자는 평가시 불린형으로 형변환 후 ➡️ 변환 후 값이 false 면 평가를 멈추고 **`false`로 평가된 값의 원래 값을 반환한다**

```js
result = value1 && value2 && value3;
```

> ❓ 피연산자가 모두 `true`로 평가되는 경우

- 가장 마지막 피연산자가 반환

### AND 연산자의 피연산자가 여러개일 경우?

- 아래 코드에서 첫번째 `false`를 반환하는게 AND연산자이므로, `null`을 반환한다

```js
alert(1 && 2 && null && 3); // null
```

- 세값이 전부 true로 평가되는 값인 경우 가장 마지막 값인 3을 반환하고 있다

```js
alert(1 && 2 && 3); // 마지막 값, 3
```
