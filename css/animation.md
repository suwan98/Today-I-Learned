# 애니메이션

## 1.애니메이션의 정의

애니메이션 효과는 HTML 요소에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 변화시킨다
애니메이션 프로퍼티는 하나의 줄거리를 구성하과
줄거리 내의 세부 움직임을 시간단위로 제어하고, 전체 줄거리의 재생 및 정지 반복까지 제어할 수 있다

<br />
<hr />
<br />

## 2. `animation property`



프로퍼티 | 설명 | 기본값
------- | ------- | -------
`animation-name` | @keyframes 애니메이션 이름을 지정한다 |  <span span style="color:red">필수 속성</span>
`animation-duration` | 한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다. | 0s  <br /> <span span style="color:red">필수 속성</span>
`animation-timing-function` | 애니메이션 효과를 위한 타이밍 함수를 지정한다. | ease
`animation-delay` | 요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다 | 0s
`animation-iteration-count` | 애니메이션 재생 횟수를 지정한다. | 1
`animation-direction` | 애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정한다. | normal
`animation-fill-mode` | 애니메이션 미실행 시(종료 또는 대기) 요소의 스타일을 지정한다. |  
`animation-play-state` | 애니메이션 재생 상태(재생 또는 중지)를 지정한다. | running
`animation` | 모든 애니메이션 프로퍼티를 한번에 지정한다 (shorthand syntax) |  
<hr />

<br />

## 2.1 @Keyframes

<br />


-  CSS animation에서 **필수 속성**이며 
-  해당 keyFrame으로 애니메이션의 흐름 중의 여러 시점에서 CSS 프로퍼티 값을 지정할 수 있다

<br />


  ```css
      @keyframes move {
      /* keyframe */
      from {
        left: 0;
      }
      /* keyframe */
      to {
        left: 300px;
      }
    }

  ```

<br />


 -  `from, to` 키워드 대신 `%`를 사용할 수 있다. 또한 시작과 끝 키프레임 사이에 % 단위로 키프레임을 삽입 할 수 있다

<br />


```css
@keyframes move {
  0%   { left: 0; }
  50%  { left: 100px; }
  100% { left: 300px; }
}
```

<br />


## 2.2 animation-name
   
 - `CSS animatio`n에서 **필수 속성**
   - `@keyframes` 뒤에 애니메이션을 대표하는 임의의 이름를 부여
   -  `animation-name: move`, @keyframe을 설정했다면 애니메이션을 주고자하는 요소에 해당 속성을 지정해야 애니메이션 효과를 부여할 수 있다

<br />


## 2.3 animation-duration

<br />


한 싸이클의 애니메이션에 소요되는 시간
s/ms로 지정한다

 ```css
    animation-duration: .5s;
    animation-duration: 500ms;
```

<br />


## 2.4 animation-timing-function

<br />


- 애니메이션 효과를 위한 수치 함수를 지정한다

<br />


## 2.5 animation-delay

<br />


- 애니메이션 이 시작하기 전에 `delay(지연)` 시간을 정할 수 있다
- 기본단위는 `s/ms`

<br />


## 2.6 animation-iteration-count
- 애니메이션의 재생 횟수를 지정하다
- 기본값은 1이고 infinite로 무한반복 할 수 있다
  
<br />


## 2.7 animation-direction

<br />

- 애니메이션이 종료된 이 후에 반복 될 때 진행하는 방향을 지정한다
  
<br />


프로퍼티값 | 설명
------|---
`normal` | 기본값으로 from(0%)에서 to(100%) 방향으로 진행한다.
`reverse` | to에서 from 방향으로 진행한다.
`alternate` | 홀수번째는 normal로, 짝수번째는 reverse로 진행한다.
`alternate-reverse` | 홀수번째는 reverse로, 짝수번째는 normal로 진행한다.

<br />


## 2.8 animation-fill-mode

<br />


- 애니메이션 미 실행시(대기 또는 종료) 요소의 스타일을 지정한다
  
<br />



프로퍼티값 | 상태 | 설명
------|----|---
`none` | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.
  | 종료 | 애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.
`forwards` | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.
  | 종료 | 종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.
`backwards` | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.
  | 종료 | 애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.
`both` | 대기 | 시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.
  | 종료 | 종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.

<br />


## 2.9 animation

<br />


- 모든 애니메이션의 프로퍼티를 한번에 지정하는 단축속성
- 값을 지정하지 않은 프로퍼티는 기본값이 지정된다
    -  지정방법
    -  ```css
        animation: name duration timing-function delay iteration-count direction fill-mode play-state```
- `animation-duration`은 **반드시 지정**해야 한다. 지정하지 않는 경우 기본값 `0s`가 셋팅되어 어떠한 애니메이션도 실행되지 않는다.


<br />