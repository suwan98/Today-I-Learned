# 타입 단언 (Type Assertion)

## 타입 단언의 정의

- `TypeScript`에서 특정 값이 어떤 유형이라고 단언(선언)하는 것을 의미
- 이러한 선언은 더 구체적인 유형으로 변환하거나/ 더 추상적인 유형으로 변환되는데 사용

## 왜 타입단언인가?

- 때로는 TypeScript가 알 수 없는 값 유형에 대한 정보를 갖게 되는 경우가 존재한다

**예시**
- `document.getElementById`를 사용하는 경우 `TypeScript`는 이것이 일종의 `HTMLElement`를 반환한다는 것만 알고 있지만 페이지에는 항상 지정된 ID를 가진 `HTMLCanvasElement`가 있다는 것을 알 수 있다

```jsx
const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement
```

- 타입 어선셜은 타입 애너테이션과 마찬가지로 컴파일 시 제거 & 코드 런타임 동작에 영향 ❌

**다음과 같이 꺾쇠 괄호 구문을 사용할 수 있다**

```ts
const myCanvas = <HTMLCanvasElement>document.getElementById("main_canvas");
```


### 타입단언 사용 시 주의점

**TypeScript는 "불가능한" 타입 어설션을 방지하기 위한 규칙을 가지고 있다**

- 아래 코드에서 `x`는 숫자타입이다.
- 이를 문자열 타입으로 변환하려고 시도하고 있다
- 그러나 이러한 변환은 불가능하므로 `Typescript`는 에러를 반환하고 이를 막아준다

```jsx
let x: number = 42;
let y: string = (x as string); // 불가능한 타입 어설션

```