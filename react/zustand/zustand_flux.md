# Zustand에서 Flux 아키텍쳐

`Zustand`는 기본적으로 `Flux` 아키텍쳐를 권장한다

## 권장되는 패턴

### 하나의 앱엔 하나의 스토어 폴더 와 파일을 정의하라

- 애플리케이션의 전역상태는 단일 `Zustand` 스토어에 위치해야 한다
- 대규모 애플리케이션의 경우 `Zustnad`는 스토어를 `slice`로 분할하는 기능을 지원

### set 함수를 통해서만 스토어 상태 업데이트 하라

- 스토어에 정의되어 있는 전역상태 업데이트를 수행하려면 `zustand`의 `set`함수를 사용하라
- `set`함수는 설명된 업데이트가 올바르게 병합되고, 수신자에게 적절하게 알림이 전송되도록 한다.

### 상태 업데이트 로직은 오직 store 파일 내부에서만 진행 하라

- `Zustand`는 `Redux`와 다르게 `dispatch` `action` 및 리듀서 함수를 사용하지 않고도 상태를 업데이트 할 수 있다
  - 이러한 스토어 액션은 스토어 내부에 직접 추가해라

```js
const useBoundStore = create((set) => ({
  storeSliceA: ...,
  storeSliceB: ...,
  storeSliceC: ...,
  updateX: () => set(...),
  updateY: () => set(...),
}))
```
