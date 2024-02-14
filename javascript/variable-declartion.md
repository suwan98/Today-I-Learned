# 변수 선언

**변수 선언이란 변수를 생성하는 것을 뜻한다**

- 값을 저장하기 위해 메모리 공간을 확보하고, 변수명과 확보된 메모리 공간의 주소를 연걸해서 값을 저장할 수 있도록 **준비**하는 것

**변수를 사용하려면 반드시 선언이 필요하다**

- `JavaScript`에서는 변수를 선언하기 위해 `var,let,const` 키워드를 제공한다.
- 변수 뿐만아닌 모든 식별자 또한 선언이 필요한데, 만약 선언하지 않고 접근하게 된다면 `Referecne Error` 즉, 참조에러가 발생할 것이다.
  - 이는 엔진이 등록된 식별자를 찾을 수 없을 때 발생하는 에러이다.

## 변수 선언의 단계들

**자바스크립트 엔진은 변수 선언을 2단계에 거쳐 수행하게 된다**

1. 선언단계 : 변수 이름을 등록해 엔진에 변수의 존재를 알린다.
2. 초기화 단계 : 값을 저장하기 위한 메모리 공간을 확보하고, 암묵적으로 `undefined`를 할당해 **초기화**한다.

## 변수명은 어디에 등록될까?

**자바스크립트의 모든 식별자는 실행 컨텍스트에 등록된다**

- 자바스크립트 엔진은 실행컨텍스트를 통해 식별자와 스코프를 관리한다.
- 변수명과 값은 실행 컨텍스트 내에서 키와밸류인 객체로 등록되어 관리된다.