# 싱글톤 패턴

## 싱글톤 패턴의 정의

**하나의 클래스에 오직 하나의 인스턴스만을 가지는 패턴**

- 하나의 클래스를 기반으로 여러개의 개별적 인스턴스를 만들 수 있지만, 그렇게 하지 않고 하나의 클래스를 기반하는 하나의 인스턴스를 만들어 이를 기반으로 로직을 구성한다.
- 데이터베이스 연결 모듈에 주로 사용된다.

## 자바스크립트 싱글톤 패턴 구현

- 아래 코드에선 Signleton.instace라는 하나의 인스턴스를 가지는 Signton 클래스를 구현했다
- 이를 통해 a와b는 하나의 공통된 인스턴스를 가질 수 있게된다.

```js
class Singleton {
  constructor() {
    if (!Singleton.instance) {
      Singleton.instance = this;
    }
    return Singleton.instance;
  }

  getInstance() {
    return this;
  }
}

const a = new Singleton();
const b = new Singleton();
console.log(a === b); // true
```

### 데이터베이스 연결 모듈

```js
const createConnection = (url) => ({url});
class DB {
  constructor(url) {
    if (!DB.instance) {
      DB.instance = createConnection(url);
    }
    return DB.instance;
  }

  connet() {
    return this.instance;
  }
}

const dbA = new DB();
const dbB = new DB();

console.log(dbA === dbB);
```

## 싱글톤 패턴에서의 단점

**싱글톤 패턴으론 TDD를 할 때 구현에 어려움이 존재한다.**

- 단위테스트 시 테스트가 서로 독립성 보장 및 어떤 순서로든 실행될 수 있어야하지만, 싱글톤 패턴으로 구현시, 미리 생성된 하나의 인스턴스를 기반으로 구현하므로 각 테스트마다의 **독립적인** 인스턴스를 생성하기 어렵다.

## 의존성 주입

- 싱글톤 패턴은 모듈간의 결합을 강하게 만들 수 있는 단점이 존재
- 이때 의존성 주입(DI - Dependency Injection)을 통해 모듈간의 결합을 느슨하게 만들어 해결 가능

> 의존성이란?

- 종속성이라고도 하며, A가 B에 의존성이 존재한다는 것은 B의 변경사항에 대해 A 또한 변경해야한다는것을 의미

### 의존성 주입의 장점

**모듈을 쉽게 교체할 수 있는 구조가 되어 테스팅이 용이하며 마이그레이션하기 수월해진다.**

- 또한 구현 시 추상화 레이어를 넣고 이를 기반으로 구현체를 넣어주므로 애플리케이션 의존성 방향이 일관되고, 쉽게 추론되고, 모듈간의 관계가 더 명확해진다.

### 의존성 주입의 단점

- 복잡도 증가
