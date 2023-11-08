# 노드 교체 메서드

## Node.prototype.replaceChild(newChild, oldChild)

**자신을 호출한 노드의 자식 노드를 다른 노드로 교체**

- 첫번째 매개변수 `newChild`에 교체할 새로운 노드를 인수로 전달
- 두번째 매개변수 `oldChild`에는 이미 존재하는 교체될 노드를 인수로 전달
  - `oldChild` 매개변수에 인수로 전달한 노드는 `replaceChild` 메서드를 호출한 노드의 자식 노드여야 한다

```tsx
<ul class="fruits">
  <li class="apple">Apple</li>
  <li class="orange">orange</li>
</ul>;

/* script */
const fruits = document.getElementById("fruits");

const newChildNode = document.createElement("li");
newChild.textContent = "Bananan";

/* fruits 요소 노드의 첫번째 자식 요소 노드를 newChild 요소 노드로 교체 */
fruits.replaceChild(newChildNode, fruits.fristElementChild);
```
