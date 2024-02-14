# createPortal

## createPortal이란?

- createPortal을 사용하면 일반적으로 렌더링 되는 index.html의 root가 아닌 index.html의 정의한 추가적인 root에서 컴포넌트를 렌더링할 수 있다.
- 주로 모달이나 툴팁등의 root 바깥에서 렌더링 될 UI를 표현하고자 할 때 사용된다.

## 사용 예시

1. 먼저 index.html에 새로운 root를 정의한다.

```html
<body class="bg-stone-50">
  <div id="modal-root"></div>
  <div id="root"></div>
  <script type="module" src="/src/main.jsx"></script>
</body>
```

2. createPortal의 첫번째 인자로는 렌더링하고자 하는 JSX, 두번째로는 렌더링하고자 하는 DOM 노드를 전달한다.

- 아래 예시에선 렌더링할 모달 jsx 코드와 modal-root DOM Node를 createPortal에서 인자로 전달하고 있는 모습이다.

```jsx
function Modal({children, buttonCaption}, ref) {
  const dialog = useRef(null);
  useImperativeHandle(ref, () => {
    return {
      open() {
        dialog.current.showModal();
      },
    };
  });

  return createPortal(
    <dialog
      ref={dialog}
      className="backdrop:bg-stone-900/90 p-4 rounded-md shadow-md">
      {children}
      <form method="dialog" className="mt-4 text-right">
        <Button>{buttonCaption}</Button>
      </form>
    </dialog>,
    document.getElementById("modal-root")
  );
}
```
