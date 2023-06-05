<h1>CSS BEM 방법론</h1>

<br />

<h2>BEM 이란?</h2>

>✍️CSS 제작 방법론으로, 개발,디버깅,유지보수를 위해 가능한 **명확하게** 네이밍하는것이 원칙이다.

<br/>
<br/>
<h2>BEM Naming Rules</h2>

**B** lock / **E**lement / **M**odifier

- 소문자,숫자 만을 조합
- 조합은 `-`(하이픈)으로 연결하여 작명 (**kebab-case**)

<hr/>

<br />

<h2>Block</h2>

- **해당 Element** 및 **Modifier**에 대한 **네임 스페이스**를 정의
- 태그,id 선택자로 사용하면 X
- **독립적인 의미를 가지는 추상화된 컴포넌트**를 의미한다(재사용성, 독립성)
- 이 블록은 상위 블록으로 생각하자
  <br/>

**⭐예시**
```html
<div class='block'>안녕 난 BEM 중에서Block을 담당해!</div>

```
  

<h2>Element</h2>

- `Block`의 구성요소로서 **특정 의미와 목적**을 가진 독립적인 의미는 없다
- `블록 이름 + 두개의 언더바(__) + 요소`로 구성된다
  <br />

**⭐예시**

  ```html
    <div class='block'>
        <span class='block__element'>
            안녕 난 BEM 중에서 Element를 담당해!
        </span>
    </div>

  ```
<h2>Modifier</h2>
  
  - 블록 또는 요소의 플래그 **생김새,행동,상태**를 바꾸는데 사용
  - `블록 또는 요소의 이름 + 두개의 하이픈(--)`로 구성된다
  - Modifier는 블록/요소 노드에 **추가하는(Extra)** 클래스 이름
  - 상태가 변경될 수 있는 요소에만 modifier 클래스를 추가하고 원래 클래스는 유지해야 한다
    <br />

**⭐예시**

```html
<div class='block'>안녕 난 BEM 중에서Block을 담당해!</div>
<!---modifier 요소 (block -->
<div class='block block--modifier'>
    안녕 난 BEM 중에서 Modifier을 담당해!
</div>
```
  