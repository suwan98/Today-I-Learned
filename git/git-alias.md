# Git 단축 명령 생성하기

- git alias를 통해 단축명령을 생성할 수 있다.
  - 이때 명령의 결과는 설정 파일에 저장된다.
  - 보통 alias는 해당 프로젝트가 아닌 전역적으로 단축해서 CLI에서 사용하는 경우가 많기 때문에, `--global`이라는 옵션과 함께 사용하는 편이다.

<br />
<br />

## git alias로 단축 명령 생성

- git의 상태를 확인하는 `git-status`를 alias를 활용해 줄여보자.

```bash
$ git config --global alias.st status
```

**git st 테스트**

- 만든 `git st`가 잘되는지 테스트하면?

![alt text](/git/assets/git-status.png)

- 정상적으로 동작하고 있는 모습이다.
