# Flex에서 Flex-item 요소들에 관한 속성

<br />

## 1. 기본적인 정의 및 개념✍️

```css
<div class="container">
	<div class="item">helloflex</div>
	<div class="item">abc</div>
	<div class="item">helloflex</div>
</div>
```
- 해당 부모요소인 container 클래스에 `display : flex`를 부여하면 <br />
- 그 순간 부터 container는 `FlexContainer` 가 되고 <br />
- 그 하위 요소인 item 클래스는 `Flex Item`이 된다 <br />
- `FlexContainer` 및 `Flex item`들은 flex가 설정 된 순간부터 `block`요소로 바뀐다. <br />
- **즉** 컨테이너가 `Flex`의 영향을 받는 **전체 공간 ** 이고 설정된 속성에 따라 각각의 아이템들을 어떤 형태로 배치되는 것

<br />

![이미지](https://studiomeal.com/wp-content/uploads/2020/01/02.jpg)

<br />


## 2. Flex-item에 적용할 수 있는 속성✍️

<br />

### flex-basis

- `flex-basis`는 flex-item의 **기본 크기**를  설정한다 <br />
- `flex-direction`이 `row` 일때는 `width`, `column` 일 때는 `height`
- `flex-basis : auto`가 기본값이다

<br />

### flex-grow

- `flex-item`이 `flex-basis`의 값 보다 커질 수 있는지를 결정한다
- `flex-grow`엔 숫자값으로 할당하는데 **0보다만 커진다면** 해당 아이템이 유연한 박스로 변하고 원래의 크기보다 커지며 빈공간을 매우게 된다
- 기본값은 0이다
  
  <br />

  ```css
    .item {
	flex-grow: 1;
	/* flex-grow: 0; */ /* 기본값 */
    }
  ```
  - 숫자의 의미는 `flex-item`들의 `flex-basis`를 **제외**한 **여백**부분을 `flex-grow`에 지정된 숫자의 비율로 나뉜다

    ```css
    /* 1:2:1의 비율로 세팅할 경우 */
    .item:nth-child(1) { flex-grow: 1; }
    .item:nth-child(2) { flex-grow: 2; }
    .item:nth-child(3) { flex-grow: 1; }
    ```
    <br />

![이미지](https://studiomeal.com/wp-content/uploads/2020/01/13-1.jpg)

<br />


### flex-shrink

- `flex-grow`와 쌍을 이루는 속성으로, **flex-item이 `flex-basis`의 값 보다 작아 질 수 있는지를 결정**
- `flex-shirnk`도 `flex-grow`와 마찬가지로 0보다 큰 값이 들어가면 해당 아이템이 **유연한 박스로 변하고 `flex-basis`보다 작아진다
- **기본값이 1**이기 때문에 따로 세팅하지 않았어도 `flex-item`이 `flex-basis`보다 작아질 수 있던것
  
<br />

```css
.item {
	flex-basis: 150px;
	flex-shrink: 1; /* 기본값 */
}
```

<br />

- `flex-shrink`를 0으로 세팅하면 해당 `flex-item`의 크기가 `flex-basis`보다 작아지지 않기 때문에 고정폭의 열을 쉽게 고정할 수 있다 해당 고정 크기는 `width`로 설정
  
```css
.container {
	display: flex;
}
.item:nth-child(1) {
	flex-shrink: 0;
	width: 100px;
}
.item:nth-child(2) {
	flex-grow: 1;
}
```

- `flex-container`의 `width`가 변경되어도 `flex-shrink:0`때문에 `컨테이너`가 아무리 작아져도 `.item(1)` 은 찌그러지지 않고 `width` 100px를 유지한다
  
<br />

### flex
- `flex-grow` + `flex-shrink` + `flex-basis`의 단축속성
-  🚨 `flex : 1`을 할당하면 flex-basis의 값은 0이된다

<br />

```css
.item {
	flex: 1;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
	flex: 1 1 auto;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
	flex: 1 500px;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```

<br />


