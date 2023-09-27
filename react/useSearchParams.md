# useSearchParams()

## useSearchParams의 정의

React-Router에서 제공하는 `hook`
현재 URL의 쿼리 매개변수를 읽고 조작하는데 사용된다.

- 브라우저의 주소 표시줄에 있는 쿼리 문자열을 읽어오고(get, 1번째), 쿼리 매개변수를 업데이트 할 수 있는 함수(set,2번째)를 반환한다

첫번째 원소는 쿼리파라미터를 조회하거나 수정하는 메서드들이 담긴 객체를 반환

- `get` 메서드를 통해 특정 쿼리파라미터를 조회할 수 있고,
- `set` 메서드를 통해 특정 쿼리파라미터를 업데이트할 수 있다.

## useSearchParams의 사용예제

**코드로직**

- 아래 코드에선 `useSearchParams` 훅을 사용해 현재 URL의 쿼리 매개변수를 가져오고,
  `setSearchParams` 함수를 사용해 쿼리 매개변수를 업데이트하고 있다.

```jsx
import {useSearchParams} from "react-router-dom";

function MyComponent() {
  const [searchParams, setSearchParams] = useSearchParams();

  // 현재 URL의 쿼리 매개변수를 읽어오기
  const name = searchParams.get("name");
  const age = searchParams.get("age");

  // 쿼리 매개변수 업데이트하기
  const updateQueryParams = () => {
    setSearchParams({name: "John", age: "30"});
  };

  return (
    <div>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
      <button onClick={updateQueryParams}>Update Query Params</button>
    </div>
  );
}
```
