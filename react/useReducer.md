# useReducer란?

**useReducer는 컴포넌트에 리듀서를 추가할 수 있는 React Hook이다.**

- 해당 Hook은 React에서 `useState`보다 더 복잡한 상태를 다룰때 사용되는 방식이다.
- 주로 상태가 여러 값에 의존하거나, 다음상태가 이전상태에 의해 결정되어야 할 때 사용된다.

```js
const [state, dispatch] = useReducer(reducer, initialArg, init?)
```

- `useReducer`의 인자로는 순수한 reducer함수가 필요하고 두번째값으론 초깃값을 필요로한다.

**리듀서 함수 정의 예시**

```js
function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return {count: state.count + 1};
    case "decrement":
      return {count: state.count - 1};
    default:
      return state;
  }
}
```

**컴포넌트 단에서 사용**

```jsx
function Counter() {
  // useReducer 사용
  const [state, dispatch] = useReducer(reducer, {count: 0});

  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: "decrement"})}>-</button>
      <button onClick={() => dispatch({type: "increment"})}>+</button>
    </>
  );
}
```
