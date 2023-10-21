# DOM (문서 객체 모델)

## DOM 이란?

> **`DOM`이란, 웹 페이지의 콘텐츠 및 구조, 그리고 스타일 요소를 구조화 시켜 표현하여 프로그래밍 언어가 해당 문서에
> 접근하여 읽고 조작할 수 있도록 `API`를 제공하는 일종의 인터페이스**

- 자바스크립트같은 스크립팅 언어가 쉽게 웹 페이지에 접근하여 조작할 수 있게끔 연결시켜주는 연결고리

### DOM(문서 객체 모델)은 어떻게 생성되고 어떻게 보여질까?

**DOM은 트리 자료구조이기도 하다**

- 따라서 `HTML DOM` 혹은 `HTML DOM Tree`라고 부르기도 한다
- 트리 자료구조로 구축되므로, `HTML` 문서는 최종적으로 하나의 최상위노드에서 시작 ~> 자식노드를 가진다
  - 아래로 뻗어나가는 하향식 구조를 가진다

### document node (문서노드)

**`DOM Tree`에서 최상위 루트 노드**

- `document` 객체를 가리킨다
- `HTML`에서 `document node`는 오로지 1개만 존재

### element node (요소노드)

**모든 HTML 요소(body,div,h2...)는 `element node`이다**

- 속성 노드를 가질 수 있는 유일한 노드
- 부모-자식 관계를 가지므로 계층적구조를 이룰 수 있게 함

### attribute node (속성노드)

**모든 HTML 요소의 속성은 attribute node이다**

- 요소 노드에 대한 정보를 가지고 있음
  - 따라서 부모 노드가 아닌 해당 노드와 바인딩 되어 있음

### text node (텍스트 노드)

- 정보를 표현하며, 가장 마지막에 위치하는 자식 노드

## DOM의 데이터타입

**DOM 객체의 구성 요소**

- 프로퍼티(property)
  - `DOM` 객체의 멤버 변수 `HTML` 태그의속성을 반영
- 메서드
  - `DOM` 객체의 멤버 함수 `HTML` 태그를 동적으로 제어
- 컬렉션
  - 정보를 집합적으로 표현하는 일종의 배열
- 이벤트리스너
  - `HTML` 태그에 작성된 이벤트 리스너들을 그대로 가진다
- 스타일
  - 해당 프로퍼티를 통해 `HTML` 태그에 적용된 `CSS` 스타일 시트에 접근 가능해진다

## JavaScript DOM 접근 메서드

**DOM의 인터페이스를 이용하여 접근할 수 있다**

- `document.querySelector(selectors)`
- `document.querySelectorAll(selectors)`
- `document.getElementById(id)`
- `document.getElementByTagName(name)`
- `document.createElement(name)`
- `node.append(node)`
- `node.appendChild(node)`
- `node.remove(node)`
- `node.removeChild(node)`
- `element.innerHTML`
- `node.textContent`
- `element.setAttribute(name, value)`
- `element.getAttribute(name)`
- `element.addEventListener(type, listener)`

### 노드 생성

- `createElement()` 메서드를 사용해 `div`노드를 만들어 변수에 할당
  - 실제 적용시엔 `apeend`, `appendChild`, `insertAdjacentHTML` 등을 사용해 화면에 뿌려야함

```js
const div = document.createElement("div");
```

### 노드 붙이기

```js
document.body.append(div);
```

### 노드 변경하기

- `textContent`나 `innerHTML` 메서드 사용

```js
const div = document.createElement("div");
div.textContent = 'Hello World!'

div.innerHTML = 'Hello World!"
```
