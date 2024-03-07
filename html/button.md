# `<button>` 태그 자세히 알아보기

- HTML button 태그는 웹 내에서 사용자와 상호작용하는 역할을 한다.
  - 마우스, 키보드, 손가락, 음성 명령등을 활성화하는 대화형 요소

## Button 태그 프로퍼티

**type**

- 버튼의 동작유형을 설정한다.
- `button`, `submit`, `reset` 값이 존재한다.

**autofocus**

- 페이지 로드 시 자동으로 포커스가 해당 속성을 부여한 버튼에 가도록 설정한다.

**disabled**

- 버튼을 비활성화하는 속성
- 비활성화 된 버튼은 클릭할 수 없고, 사용자 상호작용이 불가하다.

**form**

- `form` 속성을 통해 버튼이 특정 `form`과 연결되게 할 수 있다.

```html
<form id="form1">
  <input type="text" name="name1" />
  <button type="submit" form="form2">Submit Form 2</button>
</form>

<form id="form2">
  <input type="text" name="name2" />
  <button type="submit" form="form1">Submit Form 1</button>
</form>
```

**name**

- 버튼의 이름을 지정한다.
- 폼이 서버로 제출 될 시 버튼의 이름과 값이 함께 전송되며, 서버에서 이를 구분해 처리할 수 있게한다.

**value**

- 버튼의 값을 설정한다.
- 폼이 서버로 제출될 시 버튼의 값이 함께 전송되며, 이를 서버에서처리할 수 있게한다.
