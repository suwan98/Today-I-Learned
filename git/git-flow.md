# Git Flow

## Git Flow 란?

**가장 최초로 제안된 워크플로우 방식, 대규모 프로젝트 관리에 적합한 방식이다**

- 기본 브랜치는 5가지로 구성된다

  - `feature` => `develop` => `release` => `hotfix` => `master`

  ![Alt text](./assets/git-flow.png)

### Feature

**`Develop` 브랜치에서 기능 구현 시 만드는 브랜치**

- 한 기능 단위마다 `Feature` 브랜치를 생성하는 게 원칙이다.

### Develop

**다음 releaase 버전 개발을 진행하는 브랜치**

- 추가 기능 구현 필요시, 해당 브랜치에서 다시 브랜치를 만들어 개발을 진행하고, 완료된 기능은 다시 `Develop` 브랜치로 `Merge`한다.

### Release

**`Develop` 브랜치에서 파생된 브랜치**

- `Master` 브랜치로 현재 코드가 `Merge`될 수 있는지 테스트하고, 이과정에서 발생한 버그를 고치는 공간이다.
- 확인결과 이상이 없다면, 해당 브랜치는 `Master` 브랜치와 `Merge` 한다

### Hotfix

**Mater브랜치의 버그를 수정하는 브랜치**

- 검수를 해도 릴리즈된 `Master` 브랜치에서 버그가 발견되는 경우가 존재한다.
- 이때 `Hotfix` 브랜치를 내어 버그 수정을 진행한다.
- 디버그가 완료되면 `Master`, `Develop` 브랜치에 `Merge`해주고 브랜치를 닫는다.

### Master

**릴리즈시 사용되는 최종단계의 메인 브랜치**

## 원칙

**진행 과정 중에 Merge된 feature, release, hotfix 브랜치는 닫아서 삭제하도록 한다.**
이처럼 계획적인 릴리즈를 가지고 스케줄이 짜여진 대규모 프로젝트에는 git-flow가 적합하다. 하지만 대부분 일반적인 프로젝트에서는 불필요한 절차들이 많아 생산성을 떨어뜨린다는 의견도 많은 방식