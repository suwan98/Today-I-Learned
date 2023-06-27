<h1>html form 입력서식에 대해서</h1>

> form 입력서식을 자주 사용해왔지만 아직까지 햇갈리는 부분이 많다 이참에 정리해보자❗


## 1. form? 🤔

html form은 웹에서 사용자의 입력을 처리할 때 사용되는 요소이다
html 폼은 다양한 유형의 입력 요소, 버튼 및 기타 유용한 UI 구성 요소를 사용하여 데이터를 수집하고 웹 서버로 전송 할 수 있다

```html
<form action="URL" method="POST">
  <!-- 입력 요소, 라벨, 버튼 등을 여기에 추가 -->
</form>
```
- 여기서 action은 폼 데이터가 전송될 서버의 URL을 의미한다
- method는 폼을 전송하는 방법 (주로 POST나 GET방식 사용)을 결정


<br />
<hr />
<br />



## 2. form 태그 내에서 사용될 수 있는 태그들 ✅

<br />


### 2.1 `<input>`

<br />


- 다양한 타입의 입력 요소를 만드는 데 사용
- 사용 시 type 속성을 통해 입력 유형을 설정
- 일반적인 타입으로는 text, password, email, number, tel 등이 있다

```html
<input type="text" id="username" name="username">
```

<br />


### 2.2 `<label>` 태그

<br />


- input 태그와 필수적으로 같이 써야하는 태그이며
- 폼 입력 요소에 대한 설명 또는 레이블을 생성하는데 사용한다
- 레이블은 for 속성으로 통해 input 요소의 id에 연결된다

```html
<label for="username">아이디:</label>
```

<br />


### 2.3 `<fieldset>` 태그

<br />


- 관련된 폼 요소를 그룹화 하는데 사용
- 이 태그 내부에서 legned태그를 사용하여 그룹의 제목을 설정할 수 있다

<br />


```html
<fieldset>
  <legend>관심사</legend>
  ... (입력 요소들)
</fieldset>

```
<br />


### 2.4 `<select>` 태그

<br />


- 드롭다운 목록을 만드는데 사용
- 태그 내부에 <option> 태그를 사용하여 옵션을 추가 할 수 있다

<br />

  
```html
<select id="city" name="city">
  <option value="seoul">서울</option>
  <option value="busan">부산</option>
</select>

```

<br />
<hr />
<br />


## 3. 웹 접근성을 고려한 폼 작성 ✅

<br />


### 3.1 <label> 태그를 사용한 연결

<br />


- 각 입력 요소에 대해 <label> 태그를 사용하고 for 속성으로 input의 id에 연결
- 이렇게하면 시각적으로도 연결된 텍스트와 입력요소를 연결할 수 있고 스크린리더 사용자가 이해하기 쉬워진다

<br />


```html
<label for="username">아이디:</label>
<input type="text" id="username" name="username">

```

<br />


### 3.2 `<fieldset>`과 `<legend>`

<br />


- form 내부에 `<fieldset>` 태그로 입력 요소들을 묶고, `<legend>` 태그로 그룹에 대한 제목을 설정하자
- 해당 에이전트 스타일은 `a11yHidden` 클래스를 부여해서 숨길 수 있도록 하자

<br />


```html
<fieldset>
  <legend>성별</legend>
  <input type="radio" id="male" name="gender" value="male">
  <label for="male">남성</label>
  <input type="radio" id="female" name="gender" value="female">
  <label for="female">여성</label>
</fieldset>

```

<br />


### 3.3 ARIA 속성

<br />


- 접근성 지원을 위한 추가정보를 위해 WAI-ARIA 속성을 사용하자
- 예를들어서, 입력 요소가 필수항목일 경우 `aria-required="true"`를 사용할 수 있다

<br />

```html
<input type="text" id="username" name="username" aria-required="true">

```

<br />
<hr />
<br />


## 4. form태그를 활용한 간단한 예제 ✅

<br />


```html
 <form action="/survey" method="POST">
    <fieldset>
      <legend>기본 정보</legend>
      
      <label for="name">이름:</label>
      <input type="text" id="name" name="name" required>
      
      <label for="age">나이:</label>
      <input type="number" id="age" name="age" min="1" max="120" required>
      
      <label for="email">이메일:</label>
      <input type="email" id="email" name="email">
    </fieldset>
    
    <fieldset>
      <legend>선호하는 음식</legend>

      <input type="checkbox" id="pizza" name="favorite_food" value="pizza">
      <label for="pizza">피자</label>
      <br>

      <input type="checkbox" id="sushi" name="favorite_food" value="sushi">
      <label for="sushi">초밥</label>
      <br>

      <input type="checkbox" id="pasta" name="favorite_food" value="pasta">
      <label for="pasta">파스타</label>
      <br>
    </fieldset>

    <input type="submit" value="설문 제출">
  </form>
```
<br />


- 폼은 두 개의 `<fieldset>`으로 구성되어 있으며, 각 `<fieldset>`은 `<legend>` 태그를 사용하여 제목을 지정
- 첫 번째 `<fieldset>`에는 이름, 나이, 이메일을 입력받는 기본 정보 사용자 입력 필드
- 두 번째 `<fieldset>`에서는 사용자의 선호하는 음식을 선택할 수 있는 체크박스를 제공
- 각 `<input>` 요소에는 특정 정보를 입력받기 위한 `<label>`이 연결 이를 통해 사용자가 이해하기 쉽고 접근하기 쉬운 폼을 만들 수 있다

<br />