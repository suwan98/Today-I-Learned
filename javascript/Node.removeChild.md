# Node.removeChild() 메서드

## removeChild 정의

- DOM Node에서 자식노드를 제거하고 제거된 노드를 반환한다

```js
<ul class="ul">
    <li></li>
<ul/>

const ul = document.queryselector('.ul')
const li = document.queryselector('li')

ul.removeChild(li)

```