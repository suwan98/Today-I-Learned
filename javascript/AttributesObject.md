# 어트리뷰트 노드와 attributes 프로퍼티

## 개요

**HTML 문서 구성 요소인 HTML 요소는 여러개의 속성을 가질 수 있다**

- HTML 어트리뷰트는 HTML 요소의 시작 태그에 `어트리뷰트 이름=”어트리뷰트 값”`형식으로 정의
- 글로벌 어트리뷰트(`id`,`class`,`style`,`title`,`hidden` 등)과 이벤트 핸들러 어트리뷰트(`onClick`, `onChange`, `onfocus`) 은 모든 HTML 요소에서 공통적으로 사용가능 하지만
  - 특정 HTML 요소에만 한정적으로 사용가능한 어트리뷰트도 존재
- 모든 어트리뷰트 노드의 참조는 유사배열객체이자 이터러블인 `NamedNodeMap` 객체에 담겨져, 요소 노드의 `attributes`프로퍼티에 저장됨

```tsx
/* user의 어트리뷰트 */
<input id="user" type="text" value="seju"></input>
```

## Element.prototype.attributes

**요소노드의 모든 어트리뷰트 노드를 어트리뷰트 노드의 참조가 담긴 NamedNodeMap 객체를 반환 받는다**

```tsx
<input id="user" type="text" value="seju"></input>

/* script */

const {attributes} = document.getElementById('user');

**/* NamedNodeMap {0 : id, 1 : type, 2: value, id: id, type: type, value : value, length :3}*/
console.log(attributes)**
```
