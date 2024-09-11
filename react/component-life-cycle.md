# 컴포넌트의 생명주기

## 1. 마운팅 (Mounting)

- `constructor()` : 컴포넌트가 초기화 될 때 호출
- `render()` : 컴포넌트가 UI를 렌더링하는 함수
- `componentDidMount()` : 컴포넌트가 DOM에 삽입 된 직후 호출되는 함수

## 2. 업데이팅 (Updating)

- `shouldComponentUp()` : 컴포넌트의 업데이트 여부를 결정하는 함수
- `render()` : 변경사항을 반영해 다시 리렌더링
- `componentDidUpdate()` : 업데이트가 완료된 후 호출되는 함수

## 3. 언마운트 (Unmount)

- `componentWillUnmount()` : 컴포넌트가 `DOM`에 제거되기 직전 호출되는 함수

## React 16 버전 이후는 Hook의 등장으로 함수형 컴포넌트에서도 생명주기와 유사한 기능을 구현할 수 있다

- `useState` : 상태틀 관리하는 Hook
- `useEffect` : 부수효과를 처리하는 Hook
