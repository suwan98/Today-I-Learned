# BFC (Block Formatting Context)

## BFC란?

- BFC는 `float` 요소의 레이아웃 위치에 대한 배치를 담당하는 개념
- 마치 레이아웃 내부 미니 레이아웃을 생성하는 것과 같이, BFC는 특정 요소를 하나의 그룹으로 묶어 독립적인 배치환경을 제공한다.

<br />

## BFC의 특징

**1. 독립적인 배치**

- BFC 내부 요소들은 주변 요소의 영향을 받지않고 자체적인 박스 모델을 기반으로 배친된다.
- 이는 마치 서로 다른 레이아웃 시스템을 사용하는것과 유사하며, 예측가능하고 일관된 레이아웃을 구성할 수 있도록 한다.

**2. 마진 겹칩 방지**

- 마진겹침현상(Margin Collaps)이란, 요소의 `margin`이 겹칠경우, 값이 더 큰 `margin`이 적용되는 현상
  - `BFC`가 아닌 자식 요소와 부모요소가 존재시, 내부 자식요소가 `margin`값을 가지면 부모 요소는 마진 겹침 현상이 발생
- 그러나 `BFC`인 부모 요소와 `margin`값을 가진 자식요소는 마진 겹침현상을 방지하므로 `BFC`인 부모요소는 내부의 높이가 더 커지게 된다.

<br />

## BFC가 생기는 조건

- html root 태그
- none을 제외한 float
- position : fixed, absolute
- display : inline-block, table, table-cell, table-caption
- overflow : visible을 제외한 모든 값
- display: floow-root
- display: flex, inline-flex, grid, inline-grid

**BFC는 요소의 레이아웃에 영향을 준다.**

- BFC는 레이아웃을 변경시키는 것보다 레이아웃 위치와 플로팅 요소를 위해 생성한다.

**BFC를 생성하는 요소는 일반적으로**

- 내부의 float과
- 외부의 float
- 마진 충돌
  을 해결하기위해 사용한다.
