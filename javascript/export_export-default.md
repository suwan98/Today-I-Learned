# export와 export default의 차이점

## export 키워드로 내보내기

**명명 내보내기**

- 단일 파일에서 여러 함수, 변수를 별도의 엔티티로 내보낼 수 있게된다
- 모든 것을 하나의 단위로 내보내는 대신 각 부분에 구체적인 이름을 정하고 개별적으로 내보낼 수 있다
- 가져올때는 내보낼 때 사용한 정확한 이름을 사용해야 한다

```js
// 📂 math.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// 📂 main.js
import {add, subtract} from "./math.js";

const result1 = add(5, 3); // result1 will be 8
const result2 = subtract(10, 4); // result2 will be 6
```

### import

**`export`로 내보낸 모듈에서 가져와야할 값이 많다면 `import * as <object>` 처럼 객체 형태로 원하는 것들을 골라 가져올 수 있다**

```js
// 📁 say.js
function sayHi(user) {
  alert(`Hello, ${user}!`);
}

function sayBye(user) {
  alert(`Bye, ${user}!`);
}

export {sayHi, sayBye}; // 두 함수를 내보냄

// 📁 main.js
import * as say from "./say.js";

say.sayHi("John");
say.sayBye("John");
```

### as 키워드

**`export`에서 `as` 키워드를 사용하면 이름을 바꿔 모듈을 가져올 수 있다**

```js
// 📁 main.js
import {sayHi as hi, sayBye as bye} from "./say.js";

hi("John"); // Hello, John!
bye("John");
```

## export default 키워드로 내보내기

**기본 내보내기**

- 해당 파일의 단일 값,함수 또는 클래스를 내보낼때
  - 즉 파일 내의 하나의 값만 내보낸다
- 다른 파일에서 해당 파일을 가져올 때 중괄호구문이 필요없어진다
- 또한 가져오기 중 하나의 파일자체를 내보내므로, 원하는 이름을 자유롭게 지정할 수 있다

```js
// 📂 math.js
const add = (a, b) => a + b;
export default add;

// 📂 main.js
import myAddFunction from "./math.js";
const result = myAddFunction(5, 10); // This will call the add function from math.js and store the result in the 'result' variable.
```

## Export VS Default Export

**차이점1**

- 내보내려하는 항목은 `export`는 무조건 중괄호로 {} 묶어서 가져와야하고,
- `export default`는 중괄호 없이 가져올 수 있다

**차이점2**

- `import` 해올 때 `export`는 내보낼때 이름을 정확히 지켜야한다
- `export default`는 이름을 자유롭게 정할 수 있다

**요점은?**

- 모듈에서 단일 값만 내보내야 하거나 모듈이 애플리케이션의 주요기능을 나타낼 경우 `export default`
- 모듈에서 여러 값을 내보내야 하거나 코드를 더 작고 재사용가능한 컴포넌트로 구성하려는 경우 `export`
