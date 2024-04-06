# useEffect

## useEffct의 일반적인 형태

- 첫번째 인수 : 실행할 부수효과가 포함된 함수
  - 해당 함수는 React가 DOM을 업데이트 한 후에 호출되며 데이터 fetching, 이벤트 리스너설정등 부수효과를 처리한다.
- 두번째 인수 : 의존성 배열
  - 배열 내 지정된 값들중 하나라도 변경되면 useEffect 내의 부수효과 함수가 다시 실행된다.
- return : 클린업 함수

```jsx
useEffect(() => {
  //do Something..

  return () => {
    // cleanup logic
  };
}, [props, state]);
```

<br />

## useEffect는 생명주기 메서드를 대체하기 위해 만들어진 훅이 아니다

**useEffct는 애플리케이션 내 컴포넌트의 여러 값들을 활용해 동기적으로 부수효과를 만드는 메커니즘이다.**
