# React Router Index 프로퍼티

```jsx
const routes = createBrowserRouter([
  {
    path: "/",
    element: <RootLayout />,
    errorElement: <ErrorPage />,
    children: [
      {index: true, element: <HomePage />},
      {
        path: "products",
        element: <ProductPage />,
      },
      {
        path: "products/:productId",
        element: <ProductDetailPage />,
      },
    ],
  },
]);
```

- 위 코드에서 `RootLayout` 컴포넌트와 `HomePage` 컴포넌트가 동일한 경로인 `/`를 기대하고 있다,
  - 이에 `HomePage` 컴포넌트에 대해서 `index:true` 프로퍼티를 설정함으로 써 해당 라우트가 루트라우트의 인덱스 라우트로 동작하게 만든다.
  - 즉 최종적으로 사용자가 루트경로에 접근시 `HomePage` 컴포넌트가 렌더링되게 된다.
- `index` 프로퍼티가 `true`로 설정된 라우트는 별도의 `path` 프로퍼티를 제공하지 않아도, 부모라우트(현재는 `/`)의 루트 경로에 매칭되는 기본라우트 역할을 한다.
