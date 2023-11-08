# 특정 노드 삭제 메서드

## Node.prototype.removeChild(child)

- 인수로 전달한 노드를 DOM에서 삭제
  - 인수로 전달한 노드는 `removeChild`를 호출한 노드의 자식노드이어야 한다

```tsx
<ul class="fruits">
  <li class="apple">Apple</li>
  <li class="orange">orange</li>
</ul>;

/* script */
const fruits = document.getElementById("fruits");

/* fruits 요소 노드의 마지막 요소를 DOM에서 삭제 */
fruits.removeChild(fruits.lastElementChild);
```
