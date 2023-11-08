# 노드 삽입 메서드 및 프로퍼티

## 마지막노드로 추가 프로퍼티

**`appendChild`**

- 인수로 전달받은 노드를 자신을 호출한 노드의 마지막 자식노드로 DOM에 추가
- 이때 노드는 추가할 위치를 지정할 수 없으며 언제나 마지막 자식 노드로 추가

```tsx
<ul class="fruits">
	<li class="apple">Apple</li>
	<li class="orange">orange</li>
</ul>

/* script */
const li = document.createElement('li');

li.appendChild(document.createTextNode('Orange'));

**/* li 요소 노드를 fruits 요소 노드의 마지막 자식으로 추가 */
document.getElementById('fruits').appendChild(li)**
```

## 지정한 위치에 노드 삽입 메서드

**`insertBefore(newNode, childNode)`**

- 첫번째 인수로 전달받은 노드를 두번째 인수로 전달받은 노드 앞에 삽입
- 두번째 인수로 전달받은 노드는 반드시 `insertBofre` 메서드를 통해 호출한 노드의 자식노드 여야함
  - 아니면 `DOMException` 에러 발생
- 두번째 인수로 전달받은 노드가 `null`이라면, 첫번째 인수로 전달받은 노드를 `insertBefore` 메서드를 호출한 노드의 마지막 자식으로 추가
  - 즉, `appendChild`와 동일하게 동작

```tsx
<ul class="fruits">
	<li class="apple">Apple</li>
	<li class="orange">orange</li>
</ul>

/* script */
const fruits = document.getElementById('fruits')
const li = document.createElement('li');
li.appendChild(document.createTextNode('Orange'));

**/* li 요소 노드를 fruits 요소 노드의 마지막 자식요소 앞에 삽입 */
fruits.inserBefore(li, fruits.lastElementChild)**
```
