# innerHTML

## innerHTML 정의 및 사용

- 요소 노드의 HTML 마크업을 취득(get)하거나 변경(set)한다
- 요소노드의 `innerHTML` 프로퍼티에 문자열 할당 시 요소 노드의 모든 자식 노드가 제거되고, 할당한 문자열에 포함되어 있는 HTML 마크업이 파싱되어 요소노드의 자식노드로 DOM에 반영

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
foo.innerHTML; // Hello <span>World!</span> World
```

**innerHTML 사용 시 HTML 마크업 문자열로 DOM 조작이 가능하다**

```tsx
<ul class="fruits">
  <li class="apple">Apple</li>
</ul>;

/* script */

const fruits = docuemnt.getElementByClassName("fruits");

/* 노드 추가 */
fruits.innerHTML += '<li class="banana">banana</li>';

/* 노드 교체 */
fruits.innerHTML = '<li class="orange">orange</li>';

/* 노드 삭제 */
fruits.innerHTML = "";
```

## innerHTML의 문제점 및 한계

**크로스 사이트 스크립팅 공격에 취약하다**

- HTML 마크업 내부에 자바스크립트 악성 코드가 포함되어 있을 시 파싱과정에서 그대로 실행될 가능성이 있기 때문

**한계점 1**

- 요소노드의 `innerHTML` 프로퍼티에 HTML 마크업 문자열을 할당하는 경우
  - 요소 노드의 모든 자식 노드를 제거하고 할당한 HTML 문자열을 파싱해 DOM을 변경한다는것
  - 아래코드에선 자식요소 `li.banana`를 추가하고 있다
  - 이때 `fruits`의 자식요소 `apple`은 아무런 변경이없으므로 다시 생성할 필요 또한 ❌
  - 그러나 `innerHTML`은 내부 자식요소를 전부 삭제하기때문에 `+=`연산자로 다시 `apple`를 만들고 거기에 `banana`를 추가하는것이다
  - 이는 효율적이지 ❌

```tsx
<ul class="fruits">
  <li class="apple">Apple</li>
</ul>;

/* script */

const fruits = docuemnt.getElementByClassName("fruits");
fruits.innerHTML += '<li class="banana">banana</li>';
```

**한계점 2**

- 새로운 요소 삽입시 삽입될 위치를 지정할 수 없다
- 아래코드와 li.apple과 li.orange 사이에 노드를 삽입하고 싶지만 `innerHTML`은 할 수 ❌
- 이를 해결하기 위해 **insertAdjacentHTML 메서드 존재**

```tsx
<ul class="fruits">
  <li class="apple">Apple</li>
  /* innerHTML은 중간에 삽입 ❌ */
  <li class="orange">orange</li>
</ul>
```
