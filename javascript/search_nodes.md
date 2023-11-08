# 노드 탐색을 위한 프로퍼티들

## 개요

**노드탐색**

- 요소 노드 취득 후 취득한 요소를 기점으로 DOM 트리의 노드를 옮기며 부모,형제,자식 노드등을 탐색할 수 있다
- DOM트리 상의 노드를 탐색할 수 있도록 자바스크립트 엔진은 `Node`,`Element` 트리 탐색 프로퍼티를 제공한다

**탐색가능한 프로퍼티들**

**node**

- `parentNode`
- `previousSibling`
- `firstChild`
- `childNodes`

**elemnt**

- `previousElementSibling`
- `nextElementSibling`

**노드 탐색프로퍼티는 모두 접근자 프로퍼티이다**

- 단, 노드 탐색 프로퍼티는 `setter` 없이 ``getter`만 존재하여 참조만 가능한 읽기전용 접근자프로퍼티

### 자식 노드 탐색

**자식노드 탐색을하기 위해선, 다음과 같은 노드 탐색 프로퍼티를 사용**

`Node.prototype.childNodes`

- 자식 노드를 모두 탐색해 `NodeList`에 담아 반환
- `NodeList`엔 요소노드 뿐만아니라 텍스트 노드도 포함될 수 있다

<br />

`Node.prototype.children`

- 자식 노드중에서 요소 노드만 모두 탐색해 `HTMLCollection`에 담아 반환
- `children` 프로퍼티가 반환한 `HTMLCollection`에는 텍스트 노드가 포함되지 ❌

<br />

`Node.prototype.firstChild`

첫번째 자식노드를 반환
반환한 자식노드는 텍스트노드이거나 요소노드일 수 있다

<br />

`Node.prototype.lastChild`

마지막 자식노드를 반환
반환한 자식노드는 텍스트노드이거나 요소노드일 수 있다

<br />

`Element.prototype.firstElementChild`

- 첫번째 자식 요소 노드를 반환

<br />

`Element.prototype.lastElementChild`

- 마지막 자식 요소 노드를 반환

### 요소 노드의 텍스트 노드 탐색

**firstChild 프로퍼티**

- 요소노드의 텍스트노드는 요소노드의 자식노드
  - 따라서 요소노드의 텍스트노드는 firstChild 프로퍼티로 접근 가능
  - 첫번째 자식노드를 반환
  - 프로퍼티가 반환한 노드는 텍스트노드이거나 요소노드이다

```tsx
<div id="foo">Hi</div>;
/* script */

docuemnt.getElementById("foo").firstChild; // Hi
```

### 부모 노드 탐색

**Node.prototype.parentNode**

- 텍스트 노드는 DOM 트리 마지막 리프노드이므로 부모노가 텍스트 노드인경우는 ❌

```tsx
<ul class="numbers">
  <li class="apple"></li>
</ul>;

/* script */
const apple = document.querySelector(".apple");
/* li클래스의 부모노드는 ul이다*/
apple.parentNode; // ul number
```

### 형제노드 탐색

**부모노드가 같은 형제노드 탐색시 아래 표와 같은 프로퍼티를 사용**

- 단, 어트리뷰트 노드는 요소노드와 연결되어있지만 부모노드가 같은 형제노드가 아니므로 반환 ❌
  - 즉, 텍스트노드 및 요소노드만 반환

| 프로퍼티                             | 설명                             |
| ------------------------------------ | -------------------------------- |
| previousSibling                      | 부모노드가 같은 형제 노드 중에서 |
| 자신의 이전 형제 노드를 탐색 후 반환 |
| nextSibling                          | 부모노드가 같은 형제 노드 중에서 |
| 자신의 다음 형제노드를 탐색 후 반환  |
| previousElementsSibling              | 부모노드가 같은 형제 노드 중에서 |

자신의 이전 형제 노드를 탐색 후 반환
(요소노드만 반환) |
| nextElementsSibling | 부모노드가 같은 형제 노드 중에서
자신의 다음 형제 노드를 탐색 후 반환
(요소노드만 반환) |
