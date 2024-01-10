# 깊은 복사를 도와주는 메서드 structuredClone

- 기본적으로 `JavaScript`에선 전개연산자로 복사나 `Object.asign`을 통한 복사는 얕은복사이다.
- 기존 깊은복사를 위해선 `lodash` 라이브러리의 `cloneDeep`함수에 의존했어야 했다.
- 그러나 `structuredClone`은 객체의 depth가 얼마나 깊던 해당 객체에 대한 깊은복사를 지원한다.

## 구문

```js
structuredClone(value);
structuredClone(value, transferables);
```

value : 복사할 대상인 원본 객체
transferables : 전송가능한 객체
