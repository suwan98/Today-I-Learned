# navigator.clipboard.writeText() 프로퍼티


## navigator.clipboard.writeText() 정의

> 참고🚨 Clipboard API는 https 또는 로컬호스트 환경에서만 동작한다

- 자바스크립트에서의 `BOM` 객체인 `navigator`의 `clipboard의` 메서드로 인수를 대상의 클립보드에 복사할 수 있는 메서드이다.
- `writeText()`는 `Promise` 객체를 리턴한다. 따라서 성공적으로 수행할 작업을 .then절에 메소드의 인자로 넘겨주거나, `async/await + try/cactch문`을 사용해도된다.

## 실제 코드로직에서의 사용

- `then`절을 사용해 `text`가 `clipboard`에 복사되었다면, 아래 `showAlert`이라는 함수를 실행하라는 성공구문을 추가하였다.

```js
const handleCopy = () => {
  const text = resultArea.textContent;

	//clipboard에 복사가 되었다면 showAlert 함수를 실행하라.
  navigator.clipboard.writeText(text).then(() => {
    showAlert('.alert-success', '클립 보드 복사 완료');
  });
};
```