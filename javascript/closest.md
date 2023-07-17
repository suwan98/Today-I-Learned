# closet()

메서드 기준 **element**에서 부터 **부모 요소 단위로 출발**하여, **각 요소가 지정한 선택자에 만족할때 까지 탐색**한다.
- 해당 값에 만족하는 요소를 리턴한다

```js
 closestElement = targetElement.closest(selectors);
```

```html
<body>  
  <div id = "div1"> This is the first div element.   
      <h3 id = "h"> This is a heading inside the div. </h3>  
      <div id = "div2"> This is the div inside the div element.   
      <div id = "div3"> This is the div element inside the second div element. </div>  
      </div>  
  </div>  

```

```js
const val1 = document.getElementById("div3");  
  
const div1 = val1.closest("#div1");      
  

```