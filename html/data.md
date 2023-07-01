# data-* 접두사

`data-*`은 **사용자 지정 데이터 특성**이라는 특성 클래스를 형성함으로 
임의의 데이터를 스크립트로 `HTML`과 `DOM`사이에서 교환할 수 있는 방법


```html
<ul>
    <!--data-id라는 접두사-->
    <li data-id="10784">Jason Walters, 003: Found dead in "A View to a Kill".</li> 
</ul>
```

<br />
<hr />
<br />

## ✅ 사용자가 임의로 명명한 속성임을 표현하는 접두어

- `<image>` 태그에서는 이미지의 너비와 높이를 지정하는 width,height 속성을 가질 수 있고 `<input>` 태그는 입력값의 `type`을 정하는 `type`이라는 속성을 가질 수 있다
- 그럼 태그내에 기존 HTML에 존재하지 않던 속성을 마음대로 정할 수 있을까?
- 정답은 ❌
  - **임의로 정한 속성**은 **사전에 약속된 속성들과의 차이**를 둬야한다

- 사전에 약속된 속성들과의 차이를 두는 것이 `data-*` 접두사이다

<br />
<hr />
<br />

## ✅ 임의의로 정한 속성에 접근하는 방법은?

- `data-*` 속성으로 할당한 값은 `dataset`이라는 프로퍼티로 접근이 가능하다
- `dataset`은 객체형태로 리턴되며, 문서내에 `data-*`라고 속성을 명시한 속성들을 전부 가져온다 
- 해당 속성을 받아와 리턴시 카멜케이스로 치환된다

```javascript
    <article
    data-name="calendar"
    data-released-date="2023-07-01"
    >
    오늘의 날짜
    </article>

    <script>
    const article = document.querySelector("article");
    console.log(article.dataset);
    // dataset으로 전부 가져온 속성들은 카멜케이스로 치환됨
    // DOMStringMap {author: "chanmin", releasedDate: "2021-02-13"} 
    </script>
```
