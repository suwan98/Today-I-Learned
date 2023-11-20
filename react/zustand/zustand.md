# Zustand

## Zusatnd란?

- 전역상태 관리 라이브러리 중 하나
- `hook` 기반의 `Zustand` 전용 `API` 제공
- 보일러플레이트가 (다른 상태관리 라이브러리에 비해)적고, 명시적이다

## Zustatnd 인스톨레이션

```bash
pnpm add zustand
```

### store 폴더 내 파일 생성

**해당 폴더 내 파일은 Zustand에서 `hook`으로 사용된다**

```js
import {create} from "zustand";

const useStore = create((set) => ({
  bears: 0,
  increasePopulation: () => set((state) => ({bears: state.bears + 1})),
  removeAllBears: () => set({bears: 0}),
}));
```

### 컴포넌트에 바인딩하기

- `Provider`로 래핑하지 않아도 어디서나 `store`에서 정의한 `hook`을 사용할 수 있다
- 상태를 선택하면 해당상태가 변경 시 해당 컴포넌트가 리렌더링된다

```js
function BearCounter() {
  const bears = useStore((state) => state.bears);
  return <h1>{bears} around here...</h1>;
}

function Controls() {
  const increasePopulation = useStore((state) => state.increasePopulation);
  return <button onClick={increasePopulation}>one up</button>;
}
```
