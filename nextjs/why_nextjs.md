# 왜 Nextjs인가?

## Nextjs는?

**빠른 웹 애플리케이션을 만들 수 있는 빌딩 블록을 제공하는 `React`기반의 프레임 워크**

### 웹 애플리케이션 빌딩 블록

**기본 CRA로 애플리케이션을 구축할 때 개발자들은 어떤것들을 고려해야할까?**

- 유저인터페이스
  - 사용자와 효과적으로 상호작용하는 방법
- 라우팅
  - 사용자가 애플리케이션의 여러부분을 `Client-side-rendering`을 이용해 새로고침 없이 이동하는 방법
- 데이터 패칭
  - 효과적으로 데이터를 참조하고 핸들링하는 방법
- 렌더링
  - 정적 혹은 동적인 컨텐츠를 효과적으로 렌더링하기
- 성능
  - 사용자에게 더 나은 UX를 제공하기 위해 성능최적화 하는 방법
- 확장성
  - 데이터 및 트래픽이 증가할때 애플리케이션을 어떻게 확장해야 할지?

### 그래서 Nextjs의 기능은?

**Nextjs는 리액트의 프레임워크이다**

- 웹 애플리케이션을 생성하기 위한 빌딩블록을 제공한다

**React를 사용해 `UI`를 구축하고, `Nextjs`로 기능을 점진적으로 채택할 수 있다**

- 라우팅,패칭,성능최적화 등과 같은 일반적인 애플리케이션의 요구사항을 `Nextjs`는 해결 할 수 있다

### Nextjs가 제공하는 기능들

> **프로덕션 단계에서**

- 파일 컨벤션을 통한 간편한 라우팅 기능 제공
- Sing-page-application 이나 Server-side-rendering과 사전렌더링을 개발자가 원하는대로 채택할 수 있다
- 내장된 `TypeScript` 지원
- 따로 `TypeScript`를 인스톨할 필요없이 사용할 수 있다

> **배포 및 빌드시**

- 번들링
  - `Nextjs`는 빌드시 자동화된 번들링옵션을 제공하고 다른 번들링 옵션 설정없이 효과적으로 최적화프로세스를 진행할 수 있다
- 코드분할

  - `Nextjs`에선 기본적으로 코드분할 기능을 제공한다
  - 기존 `React`프로젝트에서 코드분할을 따로 개발자가 설정할 필요가 없어진다
  - 페이지/디렉토리 내 각 파일들은 빌드단계에서 자동적으로 자체 `JavaScript`번들로 코드 스플리팅 된다

- 이미지 최적화
  - `<Image>` 컴포넌트를 자체적으로 제공함으로 써 이미지들에 대한 최적화도 옵션으로 진행할 수 있게된다