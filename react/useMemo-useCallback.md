# useMemo와 useCallback의 정의와 차이점

## useMemo & useCallback

<hr />

**useMemo()**

- Javascript의 모든 데이터 유형을 `memoization`할 수 있다

**useCallback()**

- `Javascript`에서 함수 데이터 유형만 `memoization`할 수 있다.

`useMemo()` hook을 사용해 함수 유형의 값을 기억할 수도 있지만, 함수 유형의 값을 메모이제이션할때는 `useCallback` hook을 사용하는게 문장 구문이 간결하다.

리렌더링이 발생할 경우 특정 변수가 변할때만 `useMemo` 혹은 `useCallback`에 등록한 함수가 실행될 수 있도록 처리하면 불필요한 연산을 하지않게되 성능적으로 이점을 챙길 수 있다

> ❓ 메모이제이션(Memoizaition) 이란

- 메모이제이션이란 기존에 수행한 연산의 결과값을 어딘가에 저장해두고 동일한 입력이 들어오면 재활용할 수 있는 프로그래밍 기법
- 중복 연산을 피할 수 있기에 메모리를 조금 더쓰더라도 애플리케이션의 성능을 최적화 할 수 있다.

<br />

### useMemo()

`useMemo(() => fn, [deps])`

**메모이제이션 된 값을 반환하는 함수**

```jsx
const update = useMemo(
  () => (nextData) => {
    setData(key, nextData);
    setStorageData(nextData);
  },
  [key]
);

const remove = useMemo(
  () => () => {
    deleteData(key);
  },
  [key]
);
```

### useCallback()

**메모이제이션 된 함수를 반환**

- 자식 컴포넌트에서`props`로 함수를 전달하는 경우
- 외부에서 값을 가져오는 `api`를 호출하는 경우
- `useCallback(fn, [deps])`

```jsx
const update = useCallback(
  (nextData) => {
    setData(key, nextData);
    setStorageData(nextData);
  },
  [key]
);

const remove = useCallback(() => {
  deleteData(key);
}, [key]);
```
