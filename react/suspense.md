# Suspense 컴포넌트

- `<Suspense>` 컴포넌트는 자식 요소가 로드되기 전까지 화면에 보여줄 대체 UI를 렌더링합니다.

```jsx
<Suspense fallback={<Loading />}>
  <SomeComponent />
</Suspense>
```

### Props

- `Children` : 최종적으로 렌더링하려는 실제 UI, children의 렌더링이 지연되면 Suspense는 `fallback` 컴포넌트를 대신 렌더한다.
- `fallback` : 실제 `children`이 렌더되기 전 대신 렌더링 되는 대체 UI
- `Suspense` 컴포넌트는 `children`의 렌더링이 지연되면 자동으로 `fallback`으로 전환되고 데이터가 준비되면 `children`을 보여줍니다.
