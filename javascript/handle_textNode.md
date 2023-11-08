# 요소 노드의 텍스트 조작

## textContent 프로퍼티

**textContent**

- getter/setter 둘다 존재
  - 요소노드의 텍스트와 모든 자손 노드의 텍스트를 모두 취득하거나 변경가능-
    - 즉 참조시 부모 태그내에 있는 태그들을 무시하고 전부참조한다

```tsx
<div id="foo">
  Hello
  <span>World</span>
</div>;

/* script */

const foo =
  docuemnt.getElementById(
    "foo"
  ); /* #foo 요소 노드의 텍스트를 모두 취득 / 이때 HTML 마크업은 무시 */
foo.textContent; // Hello World
```

## nodeValue

**nodeValue 프로퍼티는 이전과 달리 참조와 할당이 모두 가능하다**

- 노드 객체의 `nodeValue` 프로퍼티 참조시 노드 객체의 값을 반환
  - 텍스트 노드의 텍스트를 반환한다는 의미
  - 텍스트노드가 아닌 노드의 `nodeValue` 프로퍼티 참조 시 `null`을 반환
- 그냥 쓸일없다
