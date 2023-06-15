# CSS object-fit 속성 이해하기✍️

<br />

> 만약에 정사각형 컨테이너 안에 프로필 이미지를 표시해야 하는 일이 생긴다면?

<br/>


## 1. ✅ object-fit 정의

<br/>


이미지나 비디오와 같은 대체요소t의 크기와 너비 측면 비율이 
부모 요소와 일치하지 않을 때 어떻게 조정할 것인지 정의한다
`object-fit` 속성은 **대체 요소**의 컨텐츠 크기에 맞고 설정한다고 한다
그렇다면 대체 요소는 무엇일까?

<br/>


### 1.1 대체 요소

<br/>


대체요소는 자신의 컨텐츠가 문서 스타일에 영향을 받지 않는 요소를 뜻한다
즉, CSS Scope에서 벗어난 콘텐츠를 의미한다
하지만 딱 **두가지**경우 CSS의 영향을 받는다

<br/>


1. 대체 요소의 위치 설정 (대체 요소의 컨텐츠 위치 ❌)
2. **컨테이너 영역 안**에서 대체 요소의 컨텐츠를 조정
   
<br/>

우리가 깊이 알아야 할것은 2번째 경우가 `object-fit` 속성과 밀접한 연관이 있는데,
해당 경우의 의미는 `<img>` 요소를 그 이미지를 감싸는 컨테이너 영역 안에서 제어할 수 있는 CSS속성이 있다는 것이다

<br/>
<hr />
<br/>

## 2. ✅ object-fit 속성 사용

- 해당 속성은 `img` 태그에 직접 `object-fit`속성을 적용하고 `cover`로 부모 요소인 컨테이너 크기를 채우는 코드이다

<br/>


```html
<section>
  <h2>4. object-fit 속성 사용</h2>
  <div class="block">
    <div class="img-wrapper">
      <img class="object-fit" src="./greater-width.jpg" alt="프로필 이미지" />
    </div>
    <div class="img-wrapper">
      <img class="object-fit" src="./greater-height.jpg" alt="프로필 이미지" />
    </div>
  </div>
  </div>
</section>
```

<br/>


```css
/* object-fit 사용 */
.object-fit {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```
<br/>
<hr />
<br/>


## 3. ✅ object-fit 속성을 사용하면 장점은?

<br/>


1. background-image 속성 대신에 이미지 태그를 사용할 경우, 
   이미지는 원본 비율을 유지하고도 잘리거나 너무 작아지지 않도록 object-fit 속성을 사용할 수 있다

2. 개발자가 이미지 리사이징 등을 직접하지 않고도 화면에 보이는 이미지의 크기와 비율을 최적화할 수 있다

<br/>