# position : relative 와 absolute✍️

<br />

  ## 1. relative?🤔

    - 동작 흐름
        1. Normal Flow를 따라 배치한 **원래 자기 자신의 위치를 기준**
        2. top, right, bottom, left의 값에 따라 최종 위치 지정
    - 값 : 양수값, 음수값 모두 줄 수 있다
    - 반대가 되는 값을 동시에 선언하면?
        - **top , bottom** 을 **동시에 선언**하면? **top만 적용**
        - **left, right**를 **동시에 선언**하면? **left만 적용**

  ## 2. absolute?🤔

    - 동작 흐름
        1. 요소를 Normal Flow에서 제거하고
        2. 가장 가까운 부모 요소를 기준으로
        - position : static이 아닌 가장 가까운 부모요소
        - 그런 요소가 없으면 body를 기준으로
        3. top,right,bottom,left 값에 따라 최종 위치 지정
    - Normal Flow에서 제거되므로
    - 마치 float처럼 새로운 레이어가 추가되어 둥둥 뜨게된다
    - 주로 기준점으로 잡고 싶은 부모를 positon:relative로 설정하고
        
        자식 요소를 position : absolute로 자주 쓴다