# FOUT (Flash of Unstyled Text) 현상

- 글자가 아예 안보이는 현상인 FOIT 현상과 달리 FOUT는 최소 글자가 보이지만, 기본 시스템 폰트가 표시되는 현상을 뜻한다.
- 이는 FOIT의 문제점을 해결하고자 글자라도 보이게하는 대안적인 해결방안이다.
- 따라서 FOUT도 폰트최적화의 우선적인 해결방안이아니다.
  - 폰트최적화를 위해 폰트 파일 압축(Woff2 포멧사용), 웹 폰트 사전 로딩등의 기법을 사용 해 폰트 최적화를 통해 UX를 향상시켜야 한다.

## FOUT 설정 방법

- 적용하고자 하는 폰트에 `font-display : swap`을 적용한다.
- 이 설정은 웹폰트가 로딩 되기전 시스템 폰트를 먼저 보여주고, 웹 폰트가 로딩 되면 이를 대체한다.

```css
@font-face {
  font-family: "나의 웹폰트";
  src: url("나의웹폰트.woff2") format("woff2"), url("나의웹폰트.woff") format("woff");
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}
```
