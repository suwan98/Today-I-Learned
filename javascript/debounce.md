# 디바운스 (Debounce)

## 디바운스 기법을 사용하는 이유

- 자바스크립트 이벤트 호출 시 `scroll`, `resize`, `input`, `mousemove`, `mouseover`등과 같은 이벤트는 짧은시간에 연속적으로 발생
  - 이러한 이벤트에 바인딩한 이벤트 핸들러는 과도하게 호출될시 성능에 문제를 야기할 수 있다.
- 디바운스는 이러한 짧은 시간 간격으로 연속적으로 호출되는 이벤트들에 대한 호출을 방지하는 프로그래밍 기법

## 디바운스 개념

**디바운스는 기본적으로 짧은시간 간격으로 이벤트가 연속으로 발생 시 이벤트 핸들러를 호출하지 않고 있다가 일정시간이 경과될 시 이벤트 핸들러가 한번만 호출되도록 한다.**

```js
function debounce(callback, delayTime) {
  let timerId;

  return () => {
    /* 이전 setTimeout에 대한 호출을 사라지게 한다 */
    if (timerId) clearTimeout(timerId);

    timerId = setTimeout(callback, delayTime);
  };
}
```

- `delayTime`보다 짧은 간격으로 이벤트가 발생 시 이전 타이머를 취소하고 새로운 타이머를 재설정한다.
- 따라서 마지막 `delayTime`보다 시간이 지나면 마지막 한번만 호출되게 된다.
