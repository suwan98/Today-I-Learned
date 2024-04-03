# Context API

<br />

## Context API란?

**리액트의 Context API는 컴포넌트 트리 안에서 데이터를 전역적으로 공유할 수 있는 방법을 제공한다.**

- 이는 주로 프롭 드릴링(즉, 상위 컴포넌트에서 하위 컴포넌트로 프롭을 단계별로 전달하는 것)의 문제를 해결하기 위해 사용 됨
- Context를 사용하면, 중간에 있는 여러 컴포넌트를 거치지 않고도 컴포넌트 트리의 깊은 곳에 있는 컴포넌트에 데이터를 직접 전달할 수 있게 된다.

<br />

### Context API의 구성 요소

**Context API는 크게 세부분으로 구성된다.**

1. createContext 함수

   - 해당 함수를 통해 새로운 Context 객체를 생성할 수 있다.
   - 이 함수는 Context의 기본값을 매개변수로 받으며, `{Provider, Consumer}` 객체를 반환한다.

2. Provider

- Context 객체에 포함된 컴포넌트
- Context를 구독하는 컴포넌트들에게 Context의 변화를 알리는 역할을 한다.
- Provider는 `value` 프로퍼티를 통해 자식 컴포넌트에게 데이터를 전달한다.

3. Cousumer

- Context의 변화를 구독하고 있는 컴포넌트
- Context 데이터가 필요한 컴포넌트는 Consumber 컴포넌트를 통해 Context의 현재 값을 읽을 수 있다.

### Context API 사용 예시

- `createContext`로 MyContext라는 Context를 생성하고, `useContext`를 통해 해당하는 값을 참조하고, 사용할 수 있게된다.

```jsx
import React, { createContext, useContext } from 'react';

const MyContext = createContext(defaultValue);

function App() {
  return (
    <MyContext.Provider value={/* 어떤 값 */}>
      <Child />
    </MyContext.Provider>
  );
}

function Child() {
  const value = useContext(MyContext);
  return <div>{value}</div>;
}


```
