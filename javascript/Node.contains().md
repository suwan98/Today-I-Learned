# Node.contains()

- 주어진 인자가 `node`의 자손인지, 아닌지에 대한 `boolean` 값을 반환한다.
  - 또한 **자손을 포함한 모든 하위노드를 확인**할 수 있다
- 자기 자신을 선택해도 true를 반환한다.
- 특정노드가 다른 노드의 자식인지를 확인하는 기능을 수행한다.

```js
node.contains(otherNode);

// childNode가 parentNode의 자손인지 확인하는 유틸리티함수
function isChildNode(parent, child) {
  if (typeof parent !== "string") {
    parent = document.querySelecotr(parent);
  }
  return parent.contains(child);
}
```
