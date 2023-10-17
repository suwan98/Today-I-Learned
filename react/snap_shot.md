# "스냅샷"같은 상태

**`state`는 읽고 쓸 수 있는 `javascript` 일반 변수 처럼 보일 수 있다**

- 그러나 `state`는 **스냅샷**처럼 동작한다
  - 상태를 변경 시도해도 이미 가지고 있는 상태가 바로 변경되진 않지만, 리렌더링을 트리거한다.

> ❓ 스냅샷?
> 사진을 찍듯이 특정 시간(시점)에 데이터 저장 장치(스토리지)의 파일 시스템을 포착해 별도의 파일이나 이미지로 저장, 보관하는 기술

<br />

## 렌더링 트리거

**사용자 이벤트에 대한 응답으로 UI가 즉시 변경될까?**

- 정답은 ❌

### 코드로직을 통해서 살펴보기

**사용자가 보내기 버튼을 클릭 시 다음 절차대로 진행**

- `onSubmit prop`에 연결된 이벤트 핸들러가 실행
- `setIsSent(true)` 함수가 실행되어 렌더링 트리거
- `React`는 요청 수신후, `isSent`상태를 업데이트하고 리렌더링

```jsx
import {useState} from "react";

export default function Form() {
  const [isSent, setIsSent] = useState(false);
  const [message, setMessage] = useState("안녕! 😃");

  if (isSent) {
    return <h1>💌 메시지가 도착했습니다!</h1>;
  }

  return (
    <form
      onSubmit={(e) => {
        e.preventDefault();
        setIsSent(true);
        sendMessage(message);
      }}>
      <textarea
        placeholder="메시지를 입력하세요."
        value={message}
        onChange={(e) => setMessage(e.target.value)}
      />
      <button type="submit">보내기</button>
    </form>
  );
}

function sendMessage(message) {}
```

**스냅샷 작동흐름 예시2**

- 해당 `setNumber`가 3번호출되어도 상태는 1회만 변경된다
  - 첫번째 렌더링 중 `number` 상태 값은 0 (=초기값)
  - `onClick` 이벤트가 실행되고, 내부에서 `setNumber` 함수가 실행되 상태 업데이트가 여러번 실행되어도,
    스냅샷 `number`의 상태값은 **여전히 0이므로 함수에 전달되는 값은 항상 0 +1**이다

```jsx
import {useState} from "react";

export default function Counter() {
  const [number, setNumber] = useState(0);

  return (
    <>
      <output>{number}</output>
      <button
        type="button"
        onClick={() => {
          setNumber(number + 1);
          setNumber(number + 1);
          setNumber(number + 1);
        }}>
        +3
      </button>
    </>
  );
}
```

<br />

## 시간 흐름에 따른 상태

**타이머를 설정해, 컴포넌트라 리렌더링 된 후에 실행하도록하면?**

- 화면의 `UI`는 state의 초깃값인 `0`으로 변하지 않는다
- 스냅샷으로 저장된 상태는 다음 렌더 전까지 그대로 값을 유지
  - 이벤트 핸들러 코드가 비동기로 처리된다해도, 상태변수의 값은 렌더 영역 내에서 절대 변경 ❌

```jsx
import {useState} from "react";

export default function Counter() {
  const [number, setNumber] = useState(0);

  return (
    <>
      <h1>{number}</h1>
      <button
        type="button"
        onClick={() => {
          setNumber(number + 5);
          setTimeout(() => alert(number), 3000); // ?
        }}>
        +5
      </button>
    </>
  );
}
```
