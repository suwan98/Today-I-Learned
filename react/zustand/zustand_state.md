# Zustand를 통한 전역 상태 업데이트

## Zustand Store 구성

**먼저 Zustand를 전역에서 사용하기 위해 store를 구성해야한다**

- `zustand`의 `create` 함수 내부에서 스토어를 생성하는것이 가장 첫번째 해야 할 일이다

- Zustand 상태에서 초기값이 될 `firstName`과 `lastName`
- 그리고 상태 업데이트 함수인 `updateFirstName`과 `updateLastName` 함수로 구성되어있다
  - `usePersonStore` 내에서 `set` 내부에서 상태가 업데이트되는 로직을 작성한다

```ts
import {create} from "zustand";

type State = {
  firstName: string;
  lastName: string;
};

type Action = {
  updateFirstName: (firstName: State["firstName"]) => void;
  updateLastName: (lastName: State["lastName"]) => void;
};
const usePersonStore = create<State & Action>((set) => ({
  firstName: "",
  lastName: "",
  updateFirstName: (firstName) => set(() => ({firstName: firstName})),
  updateLastName: (lastName) => set(() => ({lastName: lastName})),
}));

export default usePesonStore;
```

### 중첩된 객체일 경우?

**아래와 같은 프로퍼터가 중첩된 `Object`인 경우**

```ts
type State = {
  deep: {
    nested: {
      obj: {count: number};
    };
  };
};
```

**일반적인 Zustatnd에서 중첩된 객체의 프로퍼티 상태 업데이트 방법**

- `React`에서 유사하게 스프레드연산자(`...`)으로 상태 객체의 `deps`들을 일일히 얕은복사를 진행
- 새로운 상태값과 병합한다
- 해당 솔루션은 현제 얕은복사에 대한 이해도가 필요하며 이에 대해 이해가 충분할 시 `immer` 라이브러리로 넘어가도 좋다

```js
 normalInc: () =>
    set((state) => ({
      deep: {
        ...state.deep,
        nested: {
          ...state.deep.nested,
          obj: {
            ...state.deep.nested.obj,
            count: state.deep.nested.obj.count + 1
          }
        }
      }
    })),
```

**immer 라이브러리를 통한 객체 상태 업데이트**

- 많은 사람들이 중첩된 값을 업데이트 할 때 `immer`를 사용
- `immer`를 통해 전개연산자로 기존 값에 대한 상태를 복사하지 않고 바로 변경할 수 있다

```ts
  immerInc: () =>
    set(produce((state: State) => { ++state.deep.nested.obj.count })),
```
