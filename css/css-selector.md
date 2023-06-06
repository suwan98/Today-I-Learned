# CSS 선택자

CSS는 다양한 방법으로 선택자를 선택하여 특정 스타일링을 구현할 수 있다

> **전체선택자✍️**

모든 요소를 선택하여 스타일을 적용


```css
* {
  color: inherit; //상속
}
```


<br />

> **요소 선택자✍️**

**Tag**를 사용하여 선택하고 스타일을 적용

```css
body { 
	margin: 0 ;
}
```

<br />

> **클래스 선택자✍️**

**클래스 명**을 선택하고 스타일을 적용

```css
.fancy {
  font-weight: bold;
  text-shadow: 4px 4px 3px #77f;
}

ul.menu{ //ul에 메뉴
	margin: 0;
	padding-left: 0;
}
```
<br />

## ul.menu 와 ul .menu의 차이점?🤔

ul태그 안에 있는 menu라는 클래스를 **가진것**만 선택해라(**자식요소만**)

 ⇒ **`ul .menu`**

ul태그 자신의 menu라는 클래스를 가진것을 선택해라 (**자손요소**)

⇒ **`ul.menu`**

<br />

> **아이디 선택자✍️**

**아이디 명**을 선택하고 스타일을 적용

```css
#demo {
  border: red 2px solid;
}
```

<br />

> **속성 선택자✍️**

요소의 *속성의 유무*나 *속성 값의 조건*에 따라 스타일을 적용할 수 있다

```css
[lang="en"] {
  font-family: Helvetica;
}

/*  ^문서의 시작 */
a[href^="https://"] { 
  background: url("../assets/images/external-link.png") no-repeat 100% 0;
	padding-right: 30px;
}

/* $ 문서의 끝 */
a[href$=".pdf"] { 
  font-weight: 700;
}
```

<br />

> **자손 결합자✍️**

두개 또는 그 이상의 선택자를 조합하여,

가장 마지막 선택자의 조상이 존재할 경우 선택자에 스타일을 적용할 수 있다

```css
/* navigation 클래스를 가진 자손요소 */
.navigation  li { 
  padding: 0;
}
/* navigation 클래스를 가진 .men클래스의 자손요소 li만 */
.navigation .menu li{ 
	color: #ccc;
}
```

<br />

> **자식 결합자✍️**

두 개 또는 그 이상의 선택자를 조합하여,

**가장 마지막 선택자의 부모 요소가 존재할 경우** 해당 선택자에 스타일을 적용


```css
.menu > li {
  margin: 0;
}
```

<br />

> **가상 요소 선택자✍️**

선택한 요소의 일부분에 스타일을 적용할 수 있다

```css
/*가상 요소 선택자 */
.align::before {
    content: '이전 요소'; //가상컨텐츠
}

.align::after {
    content: '다음 요소'; //가상컨텐츠
}
```
나머지 가상 요소들

```css
p::first-letter{
	font-size: 3rem;
	font-weight: 700;
}

p::first-line{
	background: #000;
	color: #fff;
}

::before, ::after{
	content: "가상 요소";
}

::selection {
  background: #373e6a;
  color: #fff;
}

input::placeholder {
  opacity: 0.5;
  color: #aaa;
}

summary::marker {
  display: none
}

::backdrop {	
	background: rgba(0, 0, 0, 0.5);
}
```

<br />

>**가상 클래스 선택자 (Pseudo Class)✍️**

선택자에 추가하는 키워드 로써 선택한 요소가 **특별한 상태(hover,focus등등..)** 선택하여 스타일을 적용할 수 있다

```css
:root {
	--primary-color: #373e6a;
	--secondary-color: #ccc;
	--base-color: #fff;
}

button:hover {
  background: var(--primary-color);
  color: var(--base-color);
}

a:focus{
	outline-offset: 4px;
	outline: 2px solid var(--primary-color);
}

form:focus-within {
	border: 1px solid var(--primary-color);
	border-radius: 4px;
}

input:focus {
	outline: 0;
}

button:focus-visible {
  outline: none;
  box-shadow: 1px 1px 5px var(--primary-color);
}

input:disabled {
	border: 1px solid var(--secondary-color);
	border-radius: 4px;
	color: --secondary-color;
	cursor: not-allowed;
}

input:checked {
  border: 0;
  outline: 2px solid var(--primary-color);
}

input:valid {
  background: url("../assets/images/checked.svg") no-repeat 100% 0 / 16px 16px;
	padding-right: 36px;
}

input:invalid {
  background: url("../assets/images/warning.svg") no-repeat 100% 0 / 16px 16px;
	padding-right: 36px;
}

li:first-child {
	margin-top: 16px 0 0 0;
}

li:nth-child(n+2) {
	margin: 8px 0;
}

li:last-child {
	margin-top: 0 0 16px 0;
}
```