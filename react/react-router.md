# 라우트 정의하기

**애플리케이션 레벨에서지원하려는 라우터를 정의할 수 있다**

- 라우터의 `path` 프로퍼티를 통해 도메인 뒤에 있는 쿼리를 설정한다.
- `element`로 해당 path에 맞는 페이지 컴포넌트를 설정한다.

```jsx
import {createBrowserRouter} from "react-router-dom";
import Home from "./views/Home";

const router = createBrowserRouter([{path: "/", element: <Home />}]);
```

## RouterProvider

- 만든 router는 변수로 정의 후 `RouterProvider`컴포넌트에 `router` 프로퍼티에 할당해야한다.

![alt text](/react/assets/routerProvider.png)
