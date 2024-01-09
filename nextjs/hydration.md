# Hydration

## Nextjs의 SSR은 치명적인 문제가 존재한다.

- `HTML`을 그려줄 수 있어도 실제로 브라우저가 렌더링한것이 아니므로 `JavaScript`코드를 `DOMElement`와 매칭시켜 동적인 페이지를 구현하지 못한다는 점이다.
- 따라서 `SSR`로 인해 렌더링 된 `HTML` 페이지는 뼈대만 존재하는 *바싹 마른 형태*로 존재하게 된다.
  - 이런 *바싹 마른 페이지*에 "수분을 공급"해줄 필요가 생기는데
  - 이러한 과정을 Hydration(수분 공급)이라고 한다.

## Hydration의 진행 과정

1. `React`로 페이지를 제작한다.
2. `Nextjs`에선 `React`에서 `HTML`파일 생성을 위한 `ReactDOMServer`를 사용해 제작된 사이트의 프로덕션 단계 파일을 생성한다.
3. 만약 이때 사용자가 페이지를 보게된다면, 서버로부터 생성된 정적인 `HTML` 파일을 보게될 것이다.
4. 첫 페이지 렌더링 후 `JavaScript` 파일이 로드되고, `ReactDOM.hydrate`라는 함수는 `JavaScript`와 함께 서버에서 렌더링 되었던 `HTML` 페이지에 수분을 공급한다.
5. `Hydration` 이후, `React reconciler`가 자리를 대체하고 사이트는 상호작용이 가능해진다.

**`hydration`이 적용되면 인터렉션이 가능해진다.**

- 최종적으로 사용자는 `SSR`을 통해 `UI`를 미리 확인하고 `Hydration`을 통해 인터렉션이 가능해진다는 것이다.
