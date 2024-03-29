# 변수 선언의 실행시점과 호이스팅

## 위 코드는 어떻게 동작하게 될까?

```js
console.log(result);

var result;
```

- 코드는 인터프리터에 의해 위에서 아래로 순차적으로 실행된다.
  - 따라서 콘솔로그가 먼저 실행되고 다음 줄에 있는 `result` 변수의 선언이 실행된다.
  - 실행시점에는 아직 `result` 변수가 선언되지 않았으므로 `Reference Error`가 발생할 것처럼보이나 그렇지 않다 왜일까?

### 변수 선언은 런타임이 아닌 그 이전단계에 먼저 실행되기 때문이다.

- 엔진은 코드를 순차적으로 실행하기 전 먼저 **코드의 평가과정**을 거치며 코드를 실행하기 위한 준비를 한다.
- 이때 평가과정에서 엔진은 변수 선언을 포함한 모든 선언문을 코드에서 찾아내 먼저 실행한다.
  - 이후, 코드의 평가과정이 끝나게 되면 모든 선언문을 제외하고 소스코드를 한줄 씩 순차적으로 실행하게 된다.
- 따라서 변수 선언이 코드의 평가과정에서 먼저 실행되므로 참조에러가 아닌 `undefined`가 출력되는 것이다.

### 호이스팅

**변수 선언문이 코드의 선두로 "끌어올려진 것"처럼 동작하는 자바스크립트 고유의 특징**

- 모든 식별자는 호이스팅된다.
- 모든 선언문은 런타임 이전 평가 단계에서 먼저 실행되기 때문이다.
  - `let,const`와 같은 키워드가 실행시 참조에러를 발생시키는 것은 해당 변수들이 호이스팅 되지만 `TDZ`에 있는 상태이므로 에러가 발생하는것이다.
