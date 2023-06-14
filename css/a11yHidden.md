# a11y.css?

<br />

>  **a11yHidden이란?**
  - 화면에는 보이지 않지만 스크린리더에는 읽히기 위한 콘텐츠


## 1. a11yHidden Code

```css
/* Accessibility Styles */
.a11yHidden,
legend {
  overflow: hidden;
  position: absolute !important;
  clip: rect(0, 0, 0, 0);
  clip-path: inset(50%);
  width: 1px;
  height: 1px;
  margin: -1px;
}

```
### 1.1 여기서 궁금했던 속성들❗

- `clip: rect(0, 0, 0, 0);`
    -  `clip`: 내용을 잘라내는 영역을 설정. 
    -  `rect()` 함수를 사용해 `top, right, bottom, left` 값을 설정합니다.
    -  `0, 0, 0, 0: top, right, bottom, left` 값을 모두 `0`으로 설정해 해당 요소의 내용을 화면상에서 모두 **잘라냄**

- `clip-path: inset(50%);`
    - `clip-path`: 지정한 경로에 해당하는 부분만을 보여주도록 설정하는 CSS 속성
    - inset(): 경로를 박스 형태로 지정하기 위한 함수
    - 50%: 부모 요소의 중앙을 지정하기 위해 사용되며, 태그의 중앙 부분이 화면에 보이도록 합니다.