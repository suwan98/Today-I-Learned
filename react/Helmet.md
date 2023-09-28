# React Helemet 라이브러리

## Helmet?

- SPA의 고질적인 단점인, SEO를 향상시켜줄 수 있는 라이브러리이다
- 리액트는 SPA이기때문에 사이트를 읽을때 단 하나의 `public/index.html`만을 읽게 된다.
  - 이는 각 페이지에 대한 정보를 읽지 못한다는 단점이 존재한다

## Helemet의 컴포넌트화를 사용해서 재사용성 높이기

```jsx
import React from "react";
import {Helmet} from "react-helmet";

const SEOHelmet = ({title, description}) => (
  <Helmet>
    <title>{title}</title>
    <meta name="description" content={description} />
    <meta name="keywords" content={keywords || "기본 키워드"} />
    <meta property="og:title" content={title} />
    <meta property="og:description" content={description} />
    <meta property="og:image" content={imageUrl} />
  </Helmet>
);

export default SEOHelmet;
```

> og?

- `openGraph`의 약자로 웹 페이지가 다양한 소셜 미디어 사이트에서 어떻게 보여질지 정의하는 프로토콜
- 웹사이트 정보를 표준화된 방식으로 제공 및 그 정보를 쉽게 파싱하고 이해할 수 있도록 돕는다
