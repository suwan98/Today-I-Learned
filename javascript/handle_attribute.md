# 어트리뷰트 조작 메서드 Element.prototype.getAttribute/setAttribute

**Element.prototype.getAttribute/setAttribute**

- `attributes`프로퍼티를 통하지 않고 요소 노드에서직접 메서드를 통해 HTML 요소의 어트리뷰트 값을 취득하거나 변경할 수 있어 편리
  - 참조 ➡️ `getAttribute`
  - 변경 ➡️ `setAttribute`

```tsx
<input id="user" type="text" value="seju"></input>

/* script */

**/* getAttribute를 통해 input의 value를 취득 */
const input = document.getElementById('user')
const inputValue = input.getAttribute('value'); // seju**

**/* setAttribute를 통해 input 어트리뷰트를 변경 */
input.setAttribute('value', '손흥민')
console.log(input.getAttribute('value')) // 손흥민**
```
