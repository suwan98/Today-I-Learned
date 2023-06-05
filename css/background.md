<h1>CSS background 정리</h1>

CSS `background` 단축속성은 색상,이미지,원점,크기,반복 등 여러 배경 스타일을 한번에 지정한다

<br/>

`단축 속성`을 사용해 선언할 수 있는 8개의 배경 속성
- `background-image`
- `background-position`
- `background-size`
- `background-repeat`
- `background-attachment`
- `background-origin`
- `background-clip`
- `background-color`

<br/>
🚨매우 주관적! 내가 자주 쓰는 네가지 속성들

- `background-image`
- `background-position`
- `background-size`
- `background-repeat`

해당 코드를 `shorthand`로 축약하면?

`background : url("이미지 url") repeat속성 position속성 / size속성`

/를 쓰는이유 => `postion`과 `size`는 일부 값의 단위를 공유하므로 <br/> /로 명시적으로 구분해줘야한다 

<hr />

<h2> background-position 프로퍼티 </h2>

<br/>

`background-image`는 **좌상단**부터 이미지를 출력한다<br/>
이때 `baground-position`을 사용하면 이미지의 좌표(x,y)를 지정할 수 있다
기본값 : `background-position : 0% 0%`로 배경 이미지는 **우측 상단**에 위치하게 된다 <br/>

![이미지](https://smooth-crustacean-40b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fd8fefe0f-903e-460f-916b-931f35955e9b%2F%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-06-05_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB_10.50.57.png?id=2a77d4f7-93f9-42bb-8e28-681f2e4a3b79&table=block&spaceId=425fec13-6847-4149-b50a-076d6741f03e&width=2000&userId=&cache=v2)

<br/>
<hr/>

<h2> background-size 프로퍼티 </h2>

<br/>

요소 배경 이미지의 크기를 설정할 수 있다
<br/>

키워드 종류
- `contain` : 이미지가 잘리거나 찌그러지지 않는 한도 내에 제일 크게 설정
- `cover` : 이미지가 찌그러지지 않도 내에 제일 크게 설정, 이미지의 가로세로비가 요소와 다르다면 이미지를 세로 또는 가로 방향으로 잘라내어 빈공간이 생기지 않도록 설정


