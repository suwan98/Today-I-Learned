# Render Props 패턴

## Render Props 패턴 이해하기

- Render Props 패턴은 자식 컴포넌트에게 어떻게 렌더링 할지를 결정하는 함수를 전달하는 것을 의미한다.
  - 이 함수는 자식 컴포넌트에서 호출되며, 그 결과는 렌더링 될 요소를 반환한다.
  - 즉, Render props는 JSX를 리턴하는 함수라고 할 수 있다.

> 🪄 **Render props의 핵심개념**
>
> - 컴포넌트가 동적으로 렌더링 할 수 있도록 해주는 함수 props를 제공하는 것!

## 예제 코드로 확인하기

```jsx

//Examples
function Examples() {
  const [content, setContent] = useState("components");

  const handleSelect = (selectedButton) => {
    setContent(selectedButton);
  };

  return (
    <>
      <Section id="examples" title="Exapmles">
        <Tabs
          render={
            <>
              <TabButton onClick={() => handleSelect("components")}>
                Component
              </TabButton>
              <TabButton onClick={() => handleSelect("jsx")}>JSx</TabButton>
              <TabButton onClick={() => handleSelect("props")}>Props</TabButton>
              <TabButton onClick={() => handleSelect("state")}>State</TabButton>
            </>
          }>
          {content}
        </Tabs>

    </>
  );
}



```

```jsx
// Tabs
function Tabs({children, render}) {
  return (
    <>
      <menu>{render}</menu>
      {children}
    </>
  );
}

export default Tabs;
```

- 래퍼 컴포넌트인 Tabs의 props인 render를 확인해보면 render의 props로 TabButton 컴포넌트들을 전달하고 있는모습이다.
- 여기서 render prop은 TabButton 컴포넌트의 집합을 뜻하게 된다.
  - 이 prop은 Fragment 요소로 래핑된 하나의 JSX 요소로 평가되고, Tabs 컴포넌트 내부에서 렌더링되게 된다.
- 이렇게하면 Tabs 컴포넌트는 어떤 버튼을 렌더링해야할지에 대한 세부적인 제어를 할 수 있게 된다.

## Render Props 패턴의 장점은?

**컴포넌트의 재사용성 증가**

- 위 코드에서 Tabs 컴포넌트는 어떤 버튼이 필요한지 알필요없게 된다 즉, 주어진 render props를 렌더링하면 되므로 다양한 상황에서 사용할 수 있게된다.

**컴포넌트의 유연성을 향상**

- 'render' prop을 통해 전달된 'TabButton' 컴포넌트들은 각기 다른 'onClick' 핸들러를 가질 수 있으므로, 'Tabs' 컴포넌트는 다양한 동작을 수행할 수 있게된다.
