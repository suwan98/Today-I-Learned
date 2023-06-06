<h1> &lti&gt 태그 이슈 🤔</h1>

<br />

현재 `<i>`태그는 **시맨틱요소**로서 기술적 용어 및 관용구로 사용되어야 하지만 현재로선 *fontawesome*의 `<i>` 태그로써 남용되는 경우가 많다
<br/> 해당 *fontawesome*의 `<i>`태그를 **시맨틱** 마크업 하려면?

<br/>

[fontAwesome - accessibility](https://fontawesome.com/docs/web/dig-deeper/accessibility)  참고🚀

```html
<button type="submit">
  <span class="fa-solid fa-envelope"></span> Email Us!
</button>
```

먼저 `<i>` 태그 대신 `<span>` 태그를 사용하고,

```html
<button type="submit">
  <span class="fa-solid fa-envelope" aria-hidden="true"></span> Email Us!
</button>
```
`aria-hidden` 속성을 사용해 아이콘의 정보를 스크린리더에게 숨겨야 한다